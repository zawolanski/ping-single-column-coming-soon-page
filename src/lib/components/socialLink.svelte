<script lang="ts">
	import Fa from 'svelte-fa/src/fa.svelte';
	import type { IconDefinition } from '@fortawesome/free-brands-svg-icons';

	export let icon: IconDefinition;
	export let size = '14';
	export let label: string;
	export let link: string;
</script>

<a href={link} target="_blank" aria-label={label}>
	<Fa {size} {icon} />
</a>

<style lang="scss">
	a {
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
</style>
