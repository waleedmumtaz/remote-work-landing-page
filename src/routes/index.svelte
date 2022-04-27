<script>
	import Footer from '$lib/components/Footer.svelte';
	import Header from '$lib/components/Header.svelte';
	import Main from '$lib/components/Main.svelte';
	import Overlay from '$lib/components/Overlay.svelte';
	import { isOverlayOpen } from '$lib/stores/OverlayStore.js';
	import '../styles/global.css';
</script>

<svelte:head>
	<title>Remote Work Landing Page</title>
</svelte:head>

{#if $isOverlayOpen}
	<Overlay />
{/if}
<Header />
<Main />
<Footer />
