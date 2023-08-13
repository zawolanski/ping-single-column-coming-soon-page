<script>
	import dashboardImg from '$lib/assets/illustration-dashboard.png';
	import Logo from '$lib/assets/logo.svelte';
	import Footer from '$lib/components/footer.svelte';
	import Form from '$lib/components/form.svelte';
	import Text from '$lib/components/text.svelte';
</script>

<Logo />
<h1>We are launching <span>soon!</span></h1>
<Text>Subscribe and get notified</Text>
<Form />
<img alt="" src={dashboardImg} />
<Footer />

<style lang="scss">
	h1 {
		font-size: 2.2rem;
		font-weight: 300;
		color: $gray;
		margin: 0 0 1.5rem;

		span {
			font-weight: 700;
			color: $very-dark-blue;
		}

		@media (min-width: $tablet-width) {
			font-size: 4.8rem;
		}
	}

	img {
		width: 100%;
		max-width: $mobile-width;
		margin-bottom: 12rem;

		@media (min-width: $tablet-width) {
			margin-bottom: 7rem;
			max-width: 60rem;
		}
	}
</style>
