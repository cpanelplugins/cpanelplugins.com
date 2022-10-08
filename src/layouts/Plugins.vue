<template>
  <Layout class="has-sidebar plugin-page" :footer="false">
    <div class="container flex flex-align-top">

      <div class="sidebar">
<h3 class="menu-item" >Categories</h3>

         <g-link class="menu-item platform-link" v-for="item in platforms"  :key="item.node.id" :to="item.node.path" >
            <g-image v-if="item.node.logo" :src="item.node.logo" :alt="item.node.title"/>
            {{ item.node.title }}
            <span class="platform-count" :class="{'platform-count--fade-out': item.node.belongsTo.totalCount == 0}">
              {{ item.node.belongsTo.totalCount }}
            </span>
          </g-link>

          <hr />

<h3 class="menu-item" >Useful cPanel Guides</h3>
<ul>
		  <li style="margin-bottom: 0px;"><a class="menu-item" target="_blank" href="https://pcx3.com/cp/how-to-create-a-cpanel-plugin/">How to create a CP plugin</a></li>
		  <li style="margin-bottom: 0px;"><a class="menu-item" target="_blank" href="https://documentation.cpanel.net/display/DD/Guide+to+cPanel+Plugins">Guide to cPanel Plugins</a></li>
		  <li style="margin-bottom: 0px;"><a class="menu-item" target="_blank" href="https://documentation.cpanel.net/display/DD/Guide+to+WHM+Plugins">Guide to WHM Plugins</a></li>
		  <li style="margin-bottom: 0px;"><a class="menu-item" target="_blank" href="https://documentation.cpanel.net/display/DD/Guide+to+Testing+Custom+Code">Testing Custom Code</a></li>
		  <li style="margin-bottom: 0px;"><a class="menu-item" target="_blank" href="https://docs.cpanel.net/whm/development/cpanel-plugin-file-generator/">Plugin File Generator</a></li>
</ul>
          <hr />
          <a href="/submit/">Add your free plugin →</a>
      </div>

      <Section class="plugins-content container flex-fit">
          <slot />
      </Section>
    </div>
  </Layout>
</template>

<static-query>
{
  platforms: allPlatform (order: ASC) {
    edges {
      node {
        id
        title
        path
        logo
        belongsTo {
          totalCount
        }
      }
    }
  }
}
</static-query>

<script>
export default {
  computed: {
    platforms () {
      return this.$static.platforms.edges.sort((a, b) => {
        return b.node.belongsTo.totalCount - a.node.belongsTo.totalCount
      })
    }
  }
}
</script>

<style lang="scss">
.plugins-content {
  padding: var(--space-x2);
}
.platform-link {
  display: flex;
  align-items: center;
  padding: 7px 0;

  img {
    width: 25px;
    height: 25px;
    vertical-align: middle;
    margin: 0 10px 0 0;
  }
}
.platform-count {
  margin-left: auto;
  padding: 0.15rem 0.4rem;
  background-color: var(--bg-teritary);
  transition: background-color .3s;
  border-radius: .3em;
  font-size: 0.7em;

  &--fade-out {
    opacity: .3;
  }
}
</style>
