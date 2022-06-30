<template>
  <Plugins>
    <h1>Professional plugins for cPanel and WHM</h1>
    <p class="mb-x2">cPanel plugins are easy to set up, compatible with older WHM versions and very easy to use. What is more, the modules can be combined in order to provide your customers with interesting product bundles like for example a VPS with additional cPanel plugins.</p>

    <!--div class="grid-cols grid-cols--3 mb">
      <PluginCard v-for="plugin in $page.defaultPlugins.edges" :key="plugin.node.id" :node="plugin.node"  />
    </div-->

    <hr />

    <h3>Recent</h3>
    <div class="grid-cols grid-cols--3">
      <PluginCard v-for="plugin in $page.plugins.edges" :key="plugin.node.id" :node="plugin.node"  />
    </div>
  </Plugins>
</template>

<script>
import Plugins from '~/layouts/Plugins.vue'
import PluginCard from '~/components/PluginCard.vue'

export default {
  components: {
    Plugins,
    PluginCard
  },
  metaInfo: {
    title: 'cPanel plugins'
  }
}
</script>

<page-query>
query {
  defaultPlugins: allPlugin (
    sort: [{ by: "index", order: ASC }]
    filter: {
      featured: {
        eq: true
      }
    }
  ) {
    edges {
      node {
        id
        title
        path
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
      }
    }
  },
  plugins: allPlugin (
    sortBy: "index"
    order: DESC
    filter: {
      featured: {
        ne: true
      }
    }
  ) {
    edges {
      node {
        id
        title
        description
        preview
        repo
        path
        screenshot  (width: 840, height:840)
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
</page-query>


