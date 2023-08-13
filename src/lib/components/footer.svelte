<script lang="ts">
	import { faFacebookF, faInstagram, faTwitter } from '@fortawesome/free-brands-svg-icons';

	import SocialLink from '$lib/components/socialLink.svelte';

	const socials = [
		{
			label: 'Facebook',
			icon: faFacebookF,
			link: 'https://www.facebook.com'
		},
		{
			label: 'Twitter',
			icon: faTwitter,
			link: 'https://twitter.com'
		},
		{
			label: 'Instagram',
			icon: faInstagram,
			link: 'https://www.instagram.com'
		}
	];
</script>

<footer>
	<div>
		{#each socials as { icon, label, link }}
			<SocialLink {icon} {label} {link} />
		{/each}
	</div>
	<p>© Copyright Ping. All rights reserved.</p>
</footer>

<style lang="scss">
	div {
		display: flex;
		justify-content: center;
		gap: 1.25rem;
		margin-inline: auto;
		margin-bottom: 2.5rem;
	}

	p {
		font-size: 1rem;
		font-weight: 300;
		color: $gray;

		@media (min-width: $tablet-width) {
			font-size: 1.2rem;
		}
	}
</style>
