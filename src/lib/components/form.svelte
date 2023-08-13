<script lang="ts">
	import Button from '$lib/components/button.svelte';
	import Input from '$lib/components/input.svelte';

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

<form on:submit|preventDefault={handleSubmit}>
	<Input
		{errorMessage}
		type="email"
		name="email"
		label="Enter your email address"
		placeholder="Your email address…"
	/>
	<Button>Notify Me</Button>
</form>

<style lang="scss">
	form {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		width: 100%;
		max-width: 28rem;
		margin-bottom: 7.2rem;

		@media (min-width: $tablet-width) {
			flex-direction: row;
			gap: 1.6rem;
			max-width: 65rem;
			margin-bottom: 9.4rem;
		}
	}
</style>
