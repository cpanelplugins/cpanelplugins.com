<template>
  <Layout class="has-sidebar docs-page" :footer="false">
    <div class="container flex flex-align-top">
      <Section class="doc-content flex-fit" container="">
        <slot></slot>
        <p>
          <a :href="editLink" target="_blank" class="github-edit-link">
            <Github />
            <span>Edit this page on GitHub</span>
          </a>
        </p>
        <nav class="docs-nav">
          <div class="docs-nav__previous">
            <g-link v-if="previousPage" exact class="button  button--small docs-nav__link" :to="previousPage.link">
              &larr; {{ previousPage.title }}
            </g-link>
          </div>
          <div class="docs-nav__next">
            <g-link v-if="nextPage" exact class="button  button--small docs-nav__link" :to="nextPage.link">
              {{ nextPage.title }} &rarr;
            </g-link>
          </div>
        </nav>
      </Section>
    </div>
  </Layout>
</template>

<script>
import Github from '~/assets/images/github-logo.svg'

export default {
  components: {
    Github
  },
  props: {
    subtitles: { type: Array, default: () => [] },
    links: { type: Array, default: () => [] }
  },
  computed: {
    currentPath () {
      return this.$route.matched[0].path
    },
    editLink () {
      let path = this.currentPath
      if((path.match(new RegExp("/", "g")) || []).length == 1) path = path + '/README'
      return `https://github.com/cpanelplugins/cpanelplugins.com/blob/master${path}.md`
    },
    items () {
      return this.links.reduce((acc, group) => (acc.push(...group.items), acc), [])
    },
    currentIndex () {
      return this.items.findIndex(item => {
        return item.link.replace(/\/$/, '') === this.$route.path.replace(/\/$/, '')
      })
    },
    nextPage () {
      return this.items[this.currentIndex + 1]
    },
    previousPage () {
      return this.items[this.currentIndex - 1]
    }
  }
}
</script>
