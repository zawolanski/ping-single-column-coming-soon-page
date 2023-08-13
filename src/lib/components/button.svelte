<script lang="ts">
	export let type: 'button' | 'reset' | 'submit' = 'submit';
</script>

<button {type}>
	<slot />
</button>

<style lang="scss">
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
		transition: background-color 0.15s;

		&:hover {
			background-color: $blue-hover;
		}

		@media (min-width: $tablet-width) {
			font-family: inherit;
			height: 5.6rem;
			border-radius: 2.8rem;
			font-size: 1.6rem;
			flex-grow: 1;
		}
	}
</style>
