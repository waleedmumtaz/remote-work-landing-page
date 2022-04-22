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
		margin-block-start: 2rem;
		margin-block-end: 1.5rem;
		padding-inline: 1.5rem;
		text-align: center;
	}

	section h1 {
		margin-block-end: 1.5rem;
	}

	section p {
		color: var(--medium-gray);
		line-height: 1.75rem;
		margin-block-end: 1.5rem;
	}

	section button {
		background-color: var(--almost-black);
		color: var(--almost-white);
		border-radius: 1rem;
		padding-inline: 1.75rem;
		padding-block: 1.25rem;
		margin-block-end: 1.5rem;
		font-size: var(--fs-paragraph);
		font-weight: var(--fw-700);
	}

	.clients img {
		width: 3.9rem;
		height: auto;
	}

	.container .clients {
		padding-inline: 1.5rem;
		padding-block-end: 2rem;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		align-items: center;
		gap: 1.5rem;
	}
</style>
