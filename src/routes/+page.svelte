<script>
	import dashboardImg from '$lib/assets/illustration-dashboard.png';
	import Logo from '$lib/assets/logo.svelte';
	import Form from '$lib/components/form.svelte';
	import Fa from 'svelte-fa/src/fa.svelte';
	import { faFacebookF, faTwitter, faInstagram } from '@fortawesome/free-brands-svg-icons';
</script>

<Logo />
<h1 class="header">We are launching <span class="header--bold">soon!</span></h1>
<p class="subheader">Subscribe and get notified</p>
<Form />
<img class="dashboardImg" alt="" src={dashboardImg} />
<footer class="footer">
	<div class="social__container">
		<a class="social__link" href="https://www.facebook.com" target="_blank" aria-label="Instagram">
			<Fa size="14" icon={faFacebookF} />
		</a>
		<a class="social__link" href="https://twitter.com/" target="_blank" aria-label="Instagram">
			<Fa size="14" icon={faTwitter} />
		</a>
		<a class="social__link" href="https://www.instagram.com" target="_blank" aria-label="Instagram">
			<Fa size="14" icon={faInstagram} />
		</a>
	</div>
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
		width: 100%;
		max-width: $mobile-width;
		margin-bottom: 12rem;
	}

	.social__container {
		display: flex;
		justify-content: center;
		gap: 1.25rem;
		margin-inline: auto;
		margin-bottom: 2.5rem;

		.social__link {
			display: flex;
			align-items: center;
			justify-content: center;
			width: 3.2rem;
			height: 3.2rem;
			border: 1px solid $pale-blue;
			border-radius: 50%;
			text-decoration: none;
			color: $blue;
			transition: background-color 0.15s, color 0.15s;

			&:hover {
				color: $white;
				background-color: $blue;
			}
		}
	}

	.copyright {
		font-size: 1rem;
		font-weight: 300;
		color: $gray;
	}

	@media (min-width: $tablet-width) {
		.header {
			font-size: 4.8rem;
		}

		.subheader {
			font-size: 2rem;
			margin-bottom: 4rem;
		}

		.dashboardImg {
			margin-bottom: 7rem;
			max-width: 60rem;
		}

		.copyright {
			font-size: 1.2rem;
		}
	}
</style>
