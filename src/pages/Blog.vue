<template>
  <Layout>
     <Section container="md" class="blog-posts">
      <div class="mb-x2 container-sm text-center">
        <h1>CpanelPlugins Blog</h1>
        <p style="opacity: .8">..bringing a personal touch to cPanel since 2021.</p>
      </div>
      <PostCard v-for="edge in $page.posts.edges" :key="edge.node.id" :post="edge.node"/>

      <p class="text-center">
        Want to contribute to our blog?
        <g-link to="https://github.com/cpanelplugins/cpanelplugins.com/blob/main/README.md#how-to-add-a-blog-post"> Learn more here</g-link>
      </p>

    </Section>
  </Layout>
</template>

<page-query>
query {
  posts: allBlogPost {
    edges {
      node {
        id
        title
        path
        date (format: "D. MMMM YYYY")
        timeToRead
        author {
          title
          path
          avatar (width: 60)
        }
        excerpt
        content
      }
    }
  }
}
</page-query>

<script>
import PostCard from '@/components/PostCard.vue'

export default {
  components: {
    PostCard
  },
  metaInfo: {
    title: 'Blog'
  }
}
</script>
