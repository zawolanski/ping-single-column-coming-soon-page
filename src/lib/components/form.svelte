<script lang="ts">
	const EMAIL_REGEXP = /^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/;
	const EMPTY = 'Whoops! It looks like you forgot to add your email';
	const INVALID = 'Please provide a valid email address';
	let errorMessage = '';

	const handleSubmit = (e: SubmitEvent) => {
		if (!e.target) return null;
		errorMessage = '';
		const formData = new FormData(e.target as HTMLFormElement);

		const data: { [key: string]: unknown } = {};
		for (let field of formData) {
			const [key, value] = field;
			data[key] = value;
		}

		const email = data.email;

		if (typeof email === 'string') {
			if (email.trim().length === 0) errorMessage = EMPTY;
			else if (!EMAIL_REGEXP.test(email)) errorMessage = INVALID;
			else errorMessage = '';
		}
	};
</script>

<form class="form" on:submit|preventDefault={handleSubmit}>
	<div>
		<input type="email" name="email" placeholder="Your email address…" aria-label="Email address" />
		{#if errorMessage !== ''}
			<p class="errorMessage">{errorMessage}</p>
		{/if}
	</div>
	<button type="submit">Notify Me</button>
</form>

<style lang="scss">
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

	@media (min-width: $desktop-width) {
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
	}
</style>
