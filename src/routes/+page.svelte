<script>
	import dashboardImg from '$lib/assets/illustration-dashboard.png';
	import Logo from '$lib/assets/logo.svelte';
</script>

<Logo />
<h1 class="header">We are launching <span class="header--bold">soon!</span></h1>
<p class="subheader">Subscribe and get notified</p>
<form class="form">
	<div>
		<input type="email" name="email" placeholder="Your email address…" aria-label="Email address" />
		<!-- <p class="errorMessage">Please provide a valid email address</p> -->
	</div>
	<button type="submit">Notify Me</button>
</form>
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

	.form {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		width: 100%;
		max-width: 28rem;
		margin-bottom: 7.2rem;

		div {
			input {
				font-family: inherit;
				height: 4rem;
				border-radius: 2rem;
				background-color: $white;
				border: 1px solid $pale-blue;
				color: $very-dark-blue;
				padding: 0 3.2rem;
				font-size: 1.2rem;
				font-weight: 300;
				width: 100%;
				box-shadow: $text-input-shadow;

				&::placeholder {
					color: $pale-blue;
				}
			}

			.errorMessage {
				text-align: center;
				color: $light-red;
				font-size: 1rem;
				margin: 0.2rem 0 0;
				font-style: italic;
				letter-spacing: 0.0125rem;
			}
		}

		button {
			font-family: inherit;
			height: 4rem;
			border-radius: 2rem;
			color: $white;
			background-color: $blue;
			border: 0;
			font-size: 1.2rem;
			font-weight: 600;
			cursor: pointer;
			box-shadow: $button-shadow;

			&:hover {
				background-color: $blue-hover;
			}
		}
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

		.form {
			flex-direction: row;
			gap: 1.6rem;
			max-width: 65rem;
			margin-bottom: 9.4rem;
			div {
				flex-grow: 1;
				input {
					height: 5.6rem;
					border-radius: 2.8rem;
					padding: 0 3rem;
					font-size: 1.6rem;
					flex-grow: 1;
				}

				.errorMessage {
					text-align: left;
					font-size: 1.2rem;
					margin: 0.6rem 0 0 2.25rem;
					letter-spacing: 0.015rem;
				}
			}

			button {
				font-family: inherit;
				height: 5.6rem;
				border-radius: 2.8rem;
				font-size: 1.6rem;
				flex-grow: 1;
			}
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
