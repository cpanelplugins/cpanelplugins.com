<template>
  <header>
    <div class="header-bar"></div>
    <div class="header-inner container flex gap-30">

      <Logo/>

      <Nav class="flex-fit"/>

      <nav class="header-actions flex">
        
		<g-link  to="/submit/" class="button primary button hide-for-small"><span>Submit a plugin</span></g-link>
        <ToggleTheme />
		<a href="/submit/" class="show-for-small" rel="noopener noreferrer" title="Submit a plugin to CpanelPlugins"><span style="margin-left:5px;" class="show-for-small">Submit a plugin</span></a>
		<!--div class="has-dropdown">
          <a
            aria-label="GitHub"
            href="/docs"
            rel="noopener noreferrer"
            target="_blank"
            title="Gridsome @ GitHub"
          ><span
             style="margin-left:5px;"
            >Support</span>
          </a>
          <div class="dropdown">
            <a href="/docs" rel="noopener noreferrer" target="_blank">
              Documentation
            </a>
            <a href="//github.com/gridsome/gridsome/issues" rel="noopener noreferrer" target="_blank">
              FAQ
            </a>
             <a href="//github.com/gridsome/gridsome/projects/2" rel="noopener noreferrer" target="_blank">
              Open Ticket
            </a>
          </div-->
        </div>
      </nav>
    </div>
  </header>
</template>

<static-query>
query {
  metadata {
    gridsomeVersion
  }
}
</static-query>

<script>
import Logo from './Logo'
import Nav from './Nav'
import ToggleTheme from '@/components/ToggleTheme.vue'
import GithubLogo from '@/assets/images/github-logo.svg'
import TwitterLogo from '@/assets/images/twitter-logo.svg'
import DiscordLogo from '@/assets/images/discord-logo.svg'
import LazyHydrate from 'vue-lazy-hydration'

export default {
  components: {
    Logo,
    GithubLogo,
    TwitterLogo,
    ToggleTheme,
    DiscordLogo,
    Nav,
    LazyHydrate
  }
}
</script>

<style lang="scss">
header {
  z-index: 20;
  position: relative;
  top: 0;
  background-color: var(--bg-transparent);
  border-bottom: 1px solid var(--border-color);
  flex-wrap: nowrap;
  position: sticky;
  transition: background-color .3s, border-color, .3s;


  .header-bar {
    background: linear-gradient(90deg, var(--primary-color) 0%,  #8ED6FB 50%, #D32E9D 100%);
    padding: 2px;
    text-align: center;
    color:#FFF;
    font-size: 1rem;

    a {
      color: currentColor;
    }
  }

  .header-inner {
    padding: 0 var(--space);
    min-height: var(--header-height);
  }

  @media screen and (min-width: 992px) and (max-resolution: 1) {
    backdrop-filter: blur(4px);
  }

  @media screen and (min-width: 992px) and (-webkit-max-device-pixel-ratio: 1) {
    backdrop-filter: blur(4px);
  }
}
</style>
