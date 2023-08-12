<script>
	import dashboardImg from '$lib/assets/illustration-dashboard.png';
	import Logo from '$lib/assets/logo.svelte';
	import Form from '$lib/components/form.svelte';
</script>

<Logo />
<h1 class="header">We are launching <span class="header--bold">soon!</span></h1>
<p class="subheader">Subscribe and get notified</p>
<Form />
<img class="dashboardImg" alt="" src={dashboardImg} />
<footer class="footer">
	<p class="copyright">© Copyright Ping. All rights reserved.</p>
</footer>

<style lang="scss">
	.header {
		font-size: 2.2rem;
		font-weight: 300;
		color: $gray;
		margin: 0 0 1.5rem;

		.header--bold {
			font-weight: 700;
			color: $very-dark-blue;
		}
	}

	.subheader {
		font-size: 1.2rem;
		font-weight: 300;
		margin: 0 0 3.2rem;
	}

	.dashboardImg {
		width: $mobile-width;
		margin-bottom: 12rem;
	}

	.copyright {
		font-size: 1rem;
		font-weight: 300;
		color: $gray;
	}

	@media (min-width: $desktop-width) {
		.header {
			font-size: 4.8rem;
		}

		.subheader {
			font-size: 2rem;
			margin-bottom: 4rem;
		}

		.dashboardImg {
			width: 100%;
			margin-bottom: 7.2rem;
		}

		.copyright {
			font-size: 1.2rem;
		}
	}
</style>
