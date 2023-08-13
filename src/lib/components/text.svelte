<p>
	<slot />
</p>

<style lang="scss">
	p {
		font-size: 1.2rem;
		font-weight: 300;
		margin: 0 0 3.2rem;
		color: $very-dark-blue;

		@media (min-width: $tablet-width) {
			font-size: 2rem;
			margin-bottom: 4rem;
		}
	}
</style>
