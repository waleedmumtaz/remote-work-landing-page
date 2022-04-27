<main>
	<div class="container">
		<div class="mobile-hero-image">
			<img src="/image-hero-mobile.png" alt="hero" />
		</div>
		<div class="desktop-hero-image">
			<img src="/image-hero-desktop.png" alt="hero" />
		</div>
		<div class="content-container">
			<div>
				<section class="content">
					<h1>Make remote work</h1>
					<p>
						Get your team in sync, no matter your location. Streamline processes, create team
						rituals, and watch productivity soar.
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
		</div>
	</div>
</main>

<style>
	.mobile-hero-image img {
		width: 100%;
		height: auto;
	}

	.desktop-hero-image img {
		display: none;
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

	.clients {
		padding-inline: 1.5rem;
		padding-block-end: 2rem;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		align-items: center;
		gap: 1.5rem;
	}

	.clients img {
		width: 3.5rem;
		height: auto;
	}

	@media (min-width: 768px) {
		.container {
			display: grid;
			grid-template-columns: 1fr 1fr;
			gap: 2rem;
			max-width: 75rem;
			padding-block: 4rem;
			margin-inline: auto;
		}

		.mobile-hero-image {
			display: none;
		}

		.desktop-hero-image {
			display: flex;
			flex-direction: column;
			justify-content: center;
		}

		.desktop-hero-image img {
			display: block;
			width: 100%;
			height: auto;
		}

		.desktop-hero-image {
			order: 99;
		}

		.content-container {
			display: flex;
			flex-direction: column;
			justify-content: center;
		}

		section {
			text-align: left;
		}

		section h1 {
			font-size: 5rem;
		}

		section p {
			max-width: 30rem;
			padding-block: 2rem;
		}

		section button:hover {
			background-color: var(--almost-white);
			color: var(--almost-black);
			outline: 1px solid var(--almost-black);
		}

		.clients {
			display: flex;
			justify-content: start;
			gap: 3rem;
			margin-block-start: 5rem;
		}

		.clients img {
			width: 5rem;
			height: auto;
		}
	}
</style>
