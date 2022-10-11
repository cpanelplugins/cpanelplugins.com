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
