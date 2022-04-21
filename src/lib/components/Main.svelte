<main>
	<div class="container">
		<div class="hero-image">
			<img src="/image-hero-mobile.png" alt="hero" />
		</div>
		<section class="content">
			<h1>Make Remote Work</h1>
			<p>
				Get your team in sync, no matter your location. Streamline processes, create team rituals,
				and watch productivity soar.
			</p>
			<button>Learn more</button>
		</section>
		<div class="clients">
			<img src="/client-databiz.svg" alt="client databiz" />
			<img src="/client-audiophile.svg" alt="client audiophile" />
			<img src="/client-meet.svg" alt="client meet" />
			<img src="/client-maker.svg" alt="client maker" />
		</div>
	</div>
</main>

<style>
	.hero-image img {
		width: 100%;
		height: auto;
	}

	section {
		margin-block-start: var(--size-8);
		margin-block-end: var(--size-4);
		padding-inline: var(--size-4);
		text-align: center;
	}

	section h1 {
		margin-block-end: var(--size-4);
	}

	section p {
		color: var(--medium-gray);
		line-height: var(--size-5);
		margin-block-end: var(--size-4);
	}

	section button {
		background-color: var(--almost-black);
		color: var(--almost-white);
		border-radius: var(--radius-3);
		padding-inline: var(--size-5);
		padding-block: var(--size-3);
		margin-block-end: var(--size-4);
		font-size: var(--fs-paragraph);
		font-weight: var(--fw-700);
	}

	.clients img {
		width: var(--size-9);
		height: auto;
	}

	.container .clients {
		padding-inline: var(--size-4);
                padding-block-end: var(--size-8);
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		align-items: center;
		gap: var(--size-4);
	}
</style>
