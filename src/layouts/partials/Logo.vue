<template>
  <div class="logo" @contextmenu="rightClick" oncontextmenu="return false;">
    <g-link class="logo__link" to="/" title="Back to home">
	<h1 class="hide-for-small" alt="CpanelPlugins.com" style="margin-top: revert;">CpanelPlugins</h1>
	<h1 class="show-for-small" alt="CpanelPlugins.com" style="margin-top: revert;">CP</h1>
    </g-link>
  </div>
</template>

<script>
export default {
  methods: {
    rightClick() {
      this.$router.push({ path: '/about' })
      return false
    }
  }
}
</script>

<style lang="scss">
 .logo {
  &__svg{
  	max-width: 130px;
  	height: auto;
    margin-top: -3px;
    &--small {
      max-width: 25px;
    }
  }
 }
</style>
