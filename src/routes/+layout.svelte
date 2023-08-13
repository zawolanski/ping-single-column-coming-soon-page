<script>
	import '@fontsource/libre-franklin/300.css';
	import '@fontsource/libre-franklin/400.css';
	import '@fontsource/libre-franklin/600.css';
	import '@fontsource/libre-franklin/700.css';
	import '../app.scss';
</script>

<div class="main-container">
	<div class="content-wrapper">
		<slot />
	</div>
</div>

<style lang="scss">
	.main-container {
		max-width: 80rem;
		margin-inline: auto;
		padding: 8rem 4rem;
	}

	.content-wrapper {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>
