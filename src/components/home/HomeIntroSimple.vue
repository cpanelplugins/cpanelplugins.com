<template>
  <Section class="intro" dots="true">
    <div class="container text-center ">

        <h1 class="intro__title">
          <span>Extend your hosting customers experience with awesome plugins for cPanel/WHM</span>
        </h1>

        <!--p class="intro__lead lead post mb">
          with our custom plugins for <g-link to="/cp/">cPanel / WHM</g-link>
        </p-->

        <p class="intro__links">
          <g-link  to="/plugins/platform/cp/" class="button primary button--large">
            <span>cPanel plugins</span>
          </g-link>
          <g-link  to="/plugins/platform/whm/" class="button secondary button--large">
            <span>WHM plugins</span>
          </g-link>
        </p>

        <p class="intro__info">
          <span>or </span>
          <a href="/developers/" rel="noopener noreferrer">
            <span>Hire cPanel Plugin Developers</span>
          </a>
        </p>
    </div>
  </Section>
</template>

<static-query>
query {
  metadata {
    gridsomeVersion
  }
}
</static-query>

<style lang="scss">
.intro {
  padding: calc(2% + var(--space)) 0;

  &__title {
    font-size: 3rem;
    font-weight: 600;
    margin-left: auto;
    margin-right: auto;

    @media screen and (max-width: 850px) {
      & {
        font-size: 2rem;
      }
    }
  }

  &__lead {
    max-width: 650px;
    margin-left: auto;
    margin-right: auto;
    font-size: 1.3rem;

    @media screen and (max-width: 850px) {
      & {
        font-size: 1rem;
      }
    }
  }

  &__info {
    font-size: .9rem;
  }

  &__keywords {
    position: relative;
    display: block;
  }
}
</style>
