<template>
  <Plugins>
    <h1>{{ $page.platform.title }} plugins</h1>

    <div class="grid-cols grid-cols--3 mb">
      <PluginCard v-for="plugin in $page.platform.belongsTo.edges" :key="plugin.node.id" :node="plugin.node"  />

      <div v-if="$page.platform.belongsTo.edges.length == 0">
        <em>Nothing here yet...</em>
      </div>
    </div>

    <hr />
    <p>
      Feel free to join the
      <a href="//discord.gg/daeay6n" rel="noopener noreferrer" target="_blank">
        #{{ $page.platform.title }}
      </a>
      community channel in Gridsome Discord.
    </p>

  </Plugins>
</template>

<page-query>
query ($id: ID!) {
  platform(id: $id) {
    title
    belongsTo(sortBy: "index") {
      edges {
        node {
          ... on Plugin {
            id
            title
            description
            preview
            repo
            path
            screenshot (width: 840, height: 840)
            platforms {
              title
              logo
            }
            author {
              title
              path
            }
          }
        }
      }
    }
  }
}
</page-query>

<script>
import Plugins from '~/layouts/Plugins.vue'
import PluginCard from '~/components/PluginCard.vue'

export default {
  components: {
    Plugins,
    PluginCard
  },
  metaInfo () {
    return {
      title: `${this.$page.platform.title} plugins`
    }
  }
}
</script>

