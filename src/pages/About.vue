<template>
  <Layout>
    <Section container="sm" class="text-center">
      <h1>About CpanelPlugins</h1>

      <p>CpanelPlugins is a github-hosted collection of awesome cPanel plugins.</p>
      <p>Built with <a href="https://github.com/gridsome/gridsome" target="_blank">Gridsome</a> and hosted on <a href="https://vercel.com/" target="_blank">Vercel</a></p>
    </Section>
	<Section container="sm">
<p>I created this website as an alternative to Cpanel AppCatalog because it hasn't been updated in years and if you want to submit a plugin, their review process takes weeks.
The website creates a plugin page for each github repo added inside plugins.yaml file</p>
<p>To get your plugin listed, your plugin must be publicly available on Github.</p>
</br>
<p>To add your plugin:</p>
<p>1. Fork <a href="https://github.com/cpanelplugins/cpanelplugins.com" target="_blank">cpanelplugins/cpanelplugins.com</a></br>
2. Add your plugin information to the <a href="https://github.com/cpanelplugins/cpanelplugins.com/edit/master/plugins/plugins.yaml" target="_blank">plugins/plugins.yaml</a> file</br>
3. Make a pull request with the following title: ADD PLUGIN</p>
</br>
    </Section>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'About CpanelPlugins.com'
  }
}
</script>

<style lang="scss">
.logo-container {
	text-align: center;
	margin-bottom: var(--space);



	&--dark {
		background-color: var(--dark-bg);
	}

  &--secondary {
    background-color: var(--primary-color-dark);
  }

	a {
		display: block;
		padding: 10%;
	}
	img {
		max-width: 320px;
		width: 100%;
		margin: 0 auto;
	} 
}

.colors {
  text-align: center;
	div {
		padding: 15% 5% 5px;
		display: inline-block;
		margin: 0 .5rem;
		text-align: center;
		color:#FFF;
    outline: 1px solid rgba(0,0,0,.1);
	}


	&__primary {
		background-color: var(--primary-color);
	}

	&__secondary {
		background-color: var(--primary-color-dark);
	}

  &__dark {
    background-color: var(--dark-bg);
  }


}

</style>
