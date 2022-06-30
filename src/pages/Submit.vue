<template>
  <Layout>
    <Section container="sm" class="text-center">
      <h1>Submit your free cpanel plugin to CpanelPlugins.com</h1>

      <p>CpanelPlugins is a github-hosted collection of free cPanel plugins.</p>
	  <p>If you are a fellow developer that has published a free cpanel plugin on Github, you can list it here and get a link back to your website.</p>
    </Section>
	<Section container="sm">
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
