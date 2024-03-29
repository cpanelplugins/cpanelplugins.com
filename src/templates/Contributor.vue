<template>
  <Layout>
    <Section container="md" class="blog-posts">

      <div class="mb-x2 container-sm text-center author-page">
        <g-image class="author-page__avatar" v-if="$page.contributor.avatar" :key="$page.contributor.id" :src="$page.contributor.avatar"/>
        <h1>{{ $page.contributor.title }}</h1>
        <p v-if="$page.contributor.bio" class="lead container-sm">
          {{ $page.contributor.bio }}
        </p>
        <a v-if="$page.contributor.twitter" :href="`https://twitter.com/${$page.contributor.twitter}`">
            {{ $page.contributor.twitter }}
        </a>
      </div>

      <h3 class="text-center" v-if="$page.contributor.posts.edges.length">Blog posts</h3>

      <PostCard v-for="edge in $page.contributor.posts.edges" :key="edge.node.id" :post="edge.node"/>

      <h3 class="text-center" v-if="$page.contributor.plugins.edges.length">Plugins</h3>

      <div class="grid-cols grid-cols--2">
        <PluginCard v-for="plugin in $page.contributor.plugins.edges" :key="plugin.node.id" :node="plugin.node" />
      </div>
    </Section>
  </Layout>
</template>

<page-query>
query ($id: ID!) {
  contributor (id: $id) {
    id
    title
    bio
    avatar (width: 124)
    twitter
    posts: belongsTo(filter: {typeName: {eq: BlogPost}}) {
      totalCount
      pageInfo {
        totalPages
        currentPage
      }
      edges {
        node {
          ...on BlogPost {
            id
            title
            path
            date (format: "D. MMMM YYYY")
            timeToRead
            author {
              id
              title
              path
            }
            excerpt
            content
          }
        }
      }
    }
    plugins: belongsTo(filter: {typeName: {eq: Plugin}}) {
      totalCount
      pageInfo {
        totalPages
        currentPage
      }
      edges {
        node {
          ...on Plugin {
              id
              title
              description
              preview
              repo
              platforms {
                title
                logo
              }
              author {
                title
                path
              }
              path
              screenshot  (width: 840, height:840)
          }
        }
      }
    }
  }
}
</page-query>

<script>
import PostCard from '@/components/PostCard.vue'
import PluginCard from '@/components/PluginCard.vue'

export default {
  components: {
    PostCard,
    PluginCard
  },
  metaInfo () {
    return {
      title: this.$page.contributor.title,
      meta: [
        {
          key: 'description',
          name: 'description',
          content: this.$page.contributor.bio
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.author-page {
  &__avatar {
    border-radius: 99px;
  }
}
</style>
