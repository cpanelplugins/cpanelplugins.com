<template>
  <Section class="home-connect">
    <div class="grid-cols flex grid-cols--2 grid-cols--gap-large">
      <div class="text-center">
        <h2>Custom cPanel Plugin Development</h2>
        <p class="lead">
          We offer a broad range of services dedicated to hosting companies using cPanel and WHM. We will customize the software for you to automate your daily tasks and help you achieve all your goals.
        </p>
        <p><g-link to="/plugins/">Hire cPanel Plugin Developers</g-link></p>
      </div>
       <div>
        <Connect />
      </div>
    </div>
  </Section>
</template>

<script>
import Connect from '~/components/Connect.vue'

export default {
  components: {
    Connect
  }
}
</script>

<style lang="scss">
.home-connect {
  @media screen and (min-width: 850px) {
    & {
      padding: 1%;
    }
  }
 .grid-cols {
    > div:first-child {
      padding: 0 5%;
    }
  }
}

</style>
