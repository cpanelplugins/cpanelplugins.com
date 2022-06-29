<template>
  <Layout>
    <Section container="sm" class="text-center">
      <h1>Safe and useful cPanel code snippets</h1>

      <p>This is a practical cPanel cheatsheet for beginners, with focus on the commands that may be useful to new sysadmins.</p>

<div class="plugins-intro container-sm post">
            <div class="plugins-intro__text">
              <p>For more commands visit <g-link to="https://pcx3.com/cheatsheets/cpanel-cheatsheet/">cPanel Cheatsheet by PC✗3</g-link></p>
            </div>
          </div>
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
