<script>
	import Header from '$lib/components/Header.svelte';
	import Main from '$lib/components/Main.svelte';
	import Overlay from '$lib/components/Overlay.svelte';
	import { isOverlayOpen } from '$lib/stores/OverlayStore.js';
	import '../styles/global.css';
</script>

{#if $isOverlayOpen}
	<Overlay />
{/if}
<Header />
<Main />
