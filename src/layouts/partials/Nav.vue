<template>
  <nav class="main-nav flex gap-15">

    <g-link to="https://www.cpanelplugins.com/" target="_self">
      <span class="main-nav__label">Home</span>
    </g-link>
    
    <g-link to="/plugins/">
      <span class="main-nav__label">Plugins</span>
    </g-link>
    
	<g-link to="/developers/">
      <span class="main-nav__label">Developers</span>
	</g-link>
  
    <g-link to="/blog/">
      <span class="main-nav__label">Blog</span>
    </g-link>
	
	<g-link to="/about/">
      <span class="main-nav__label">About</span>
    </g-link>
    
    <div class="has-dropdown">
          <a
            aria-label="Exams"
            href="/exams/"
            rel="noopener noreferrer"
            target="_self"
            title="Exams"
          ><span
             style="margin-left:5px;"
            >Exams</span>
          </a>
          <div class="dropdown">
            <a href="/exams/whm-administration-certification-exam-cwa-answers/" rel="noopener noreferrer">
              CWA
            </a>
            <a href="/exams/cpanel-whm-system-administrator-exam-cwsa-answers/" rel="noopener noreferrer">
              CWSA
            </a>
            <a href="/exams/cpanel-whm-system-administrator-2-exam-cwsa-2-answers/" rel="noopener noreferrer">
              CWSA-2
            </a>
            <a href="/exams/cpanel-certified-partner-accreditation-exam-cpcp-answers/" rel="noopener noreferrer">
              CPCP
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
