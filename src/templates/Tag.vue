<template>
  <Layout>
    <h1 class="text-xl font-semibold mb-5">{{$page.tag.title}}</h1>
    
    <ul class="list-outside list-disc">
      <li v-for="post in $page.tag.belongsTo.edges" :key="post.node.id" class="mt-3">
        <g-link :to="post.node.path">{{ post.node.title }} – {{post.node.date}}</g-link>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query Tag ($id: ID!) {
  tag: tag (id: $id) {
    title
    belongsTo {
      totalCount
      edges {
        node {
          ...on BlogPost {
            title
            date (format: "MMMM D, Y")
            path
          }
        }
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo () {
    return {
      title: 'Tag: ' + this.$page.tag.title,
    }
  },
}
</script>
