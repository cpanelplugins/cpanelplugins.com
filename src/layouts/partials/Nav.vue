<template>
  <nav class="main-nav flex gap-15">

    <g-link to="https://www.cpanelplugins.com/" target="_self">
      <span class="main-nav__label">Home</span>
    </g-link>
    
    <g-link to="/plugins/">
      <span class="main-nav__label">Plugins</span>
    </g-link>
    
	<g-link to="/developers/">
      <span class="main-nav__label">Developers<sup> <b style="color:var(--primary-color)"> NEW</b></sup></span>
	</g-link>
  
    <g-link to="/blog/">
      <span class="main-nav__label">Blog</span>
    </g-link>
	
	<g-link to="/about/">
      <span class="main-nav__label">About</span>
    </g-link>
    
    <div class="has-dropdown">
          <a
            aria-label="GitHub"
            href="/plugins/"
            rel="noopener noreferrer"
            target="_blank"
            title="Plugins"
          ><span
             style="margin-left:5px;"
            >Plugins</span>
          </a>
          <div class="dropdown">
            <a href="/plugins/platform/cp/" rel="noopener noreferrer" target="_blank">
              cPanel Plugins
            </a>
            <a href="/plugins/platform/whm/" rel="noopener noreferrer" target="_blank">
              WHM Plugins
            </a>
          </div>
  </nav>
</template>


<style lang="scss">
.main-nav {
  flex-wrap: nowrap;
}
@media screen and (max-width: 850px) {
 .main-nav {
    order: 10;
    min-width: 100%;
    a {
      padding-top: 5px;
      padding-bottom: 10px;
    }
  }
}
</style>
