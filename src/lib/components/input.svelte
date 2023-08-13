<script lang="ts">
	export let errorMessage = '';
	export let type: string = 'text';
	export let name: string;
	export let placeholder: string = '';
	export let label: string = '';
</script>

<div>
	<input
		{type}
		{name}
		{placeholder}
		class:invalid={errorMessage !== ''}
		aria-label={label}
		aria-invalid={errorMessage !== ''}
		aria-errormessage={name}
	/>
	{#if errorMessage !== ''}
		<p id={name}>{errorMessage}</p>
	{/if}
</div>

<style lang="scss">
	div {
		@media (min-width: $tablet-width) {
      width: 65%;
		}
	}

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

		&.invalid {
			border-color: $light-red;
		}

		&::placeholder {
			color: $pale-blue;
		}

		@media (min-width: $tablet-width) {
			height: 5.6rem;
			border-radius: 2.8rem;
			padding: 0 3rem;
			font-size: 1.6rem;
		}
	}

	p {
		text-align: center;
		color: $light-red;
		font-size: 1rem;
		margin: 0.2rem 0 0;
		font-style: italic;
		letter-spacing: 0.0125rem;

		@media (min-width: $tablet-width) {
			text-align: left;
			font-size: 1.2rem;
			margin: 0.6rem 0 0 2.25rem;
			letter-spacing: 0.015rem;
		}
	}
</style>
