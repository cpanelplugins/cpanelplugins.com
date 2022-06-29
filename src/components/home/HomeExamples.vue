<template>
	<Section dots="true">
		<h2 class="container text-center">
      Easy to customize and extend!
    </h2>
    <p class="lead text-center container-md">
    	All plugins on this site are open-source and can be easily customized
    </p>

		<div class="home-examples mb-x2">
			<Examples />
		</div>

    <p class="home-links text-center ">
      <g-link  to="/plugins/" class="button primary button--large">
        Get started
      </g-link>
    </p>
	</Section>
</template>

<script>
import Examples from '~/components/Examples.vue'
export default {
	components: {
		Examples
	}
}
</script>

<style>
.home-examples {
	margin: 0 auto;
	max-width: 960px;
}
</style>
