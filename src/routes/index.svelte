<script>
	import Header from '$lib/components/Header.svelte';
	import Main from '$lib/components/Main.svelte';
</script>

<svelte:head>
	<link rel="stylesheet" href="https://unpkg.com/open-props" />
	<!-- <link rel="stylesheet" href="https://unpkg.com/open-props/normalize.min.css" /> -->
</svelte:head>

<Header />
<Main />

<style>
	@import url('https://fonts.googleapis.com/css2?family=Epilogue:wght@500;700&display=swap');

	:global(:root) {
		--almost-white: hsl(0, 0%, 98%);
		--medium-gray: hsl(0, 0%, 41%);
		--almost-black: hsl(0, 0%, 8%);

		--fs-paragraph: 18px;

		--fw-500: 500;
		--fw-700: 700;

		--font-family: 'Epilogue', sans-serif;
	}

	:global(*, *::before, *::after) {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	:global(body) {
		font-family: var(--font-family);
	}

	:global(p) {
		font-size: var(--fs-paragraph);
	}

	:global(button) {
		border: none;
		background: none;
		cursor: pointer;
	}
</style>
