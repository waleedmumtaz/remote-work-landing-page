<div class="overlay">
	<slot />
</div>

<style>
	.overlay {
		min-width: 100vh;
		min-height: 100vh;
		position: fixed;
		inset: 0;
		background-color: black;
		opacity: 0.5;
		z-index: 10;
	}
</style>
