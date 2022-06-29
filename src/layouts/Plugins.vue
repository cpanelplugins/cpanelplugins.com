<template>
  <Layout class="has-sidebar plugin-page" :footer="false">
    <div class="container flex flex-align-top">

      <div class="sidebar">

          <h3 class="menu-item" >Developers</h3>

          <ul>
		  <li style="margin-bottom: 0px;"><a class="menu-item" href="/contributor/taidos/">Carlos Faustino</a></li>
		  <li style="margin-bottom: 0px;"><a class="menu-item" href="/contributor/ismaelyws/">Hans Desjarlais</a></li>
		  <li style="margin-bottom: 0px;"><a class="menu-item" href="/contributor/stefanpejcic/">Stefan Pejcic</a></li>
		  <li style="margin-bottom: 0px;"><a class="menu-item" href="/contributor/fevangelou/">Fotis Evangelou</a></li>
		  <li style="margin-bottom: 0px;"><a class="menu-item" href="/contributor/felipegabriel/">Felipe Gabriel</a></li>
		  <li style="margin-bottom: 0px;"><a class="menu-item" href="/contributor/troglodyne/">Troglodyne LLC</a></li>
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
