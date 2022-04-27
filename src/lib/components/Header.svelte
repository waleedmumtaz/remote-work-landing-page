<script>
	import { isOverlayOpen } from '$lib/stores/OverlayStore.js';
	import { fly, slide } from 'svelte/transition';

	let isMobileNavOpen = false;

	let isMobileFeaturesOpen = false;
	let isMobileCompanyOpen = false;

	let isDesktopFeaturesOpen = false;
	let isDesktopCompanyOpen = false;

	const openMobileNav = () => {
		isMobileNavOpen = true;
		isOverlayOpen.set(true);
	};

	const closeMobileNav = () => {
		isMobileNavOpen = false;
		isOverlayOpen.set(false);
	};

	const toggleMobileFeatures = () => {
		isMobileFeaturesOpen = !isMobileFeaturesOpen;
	};

	const toggleMobileCompany = () => {
		isMobileCompanyOpen = !isMobileCompanyOpen;
	};

	const toggleDesktopFeatures = () => {
		isDesktopFeaturesOpen = !isDesktopFeaturesOpen;
		isDesktopCompanyOpen = false;
	};

	const toggleDesktopCompany = () => {
		isDesktopCompanyOpen = !isDesktopCompanyOpen;
		isDesktopFeaturesOpen = false;
	};
</script>

<header>
	<div>
		<div class="nav-container">
			<a href="/#"><img src="/logo.svg" alt="logo" /></a>
			<button class="button-mobile-nav" on:click|preventDefault={openMobileNav}>
				<img src="/icon-menu.svg" alt="menu" />
			</button>

			<!-- Desktop Nav -->
			<nav class="nav-desktop">
				<ul>
					<li class="features">
						<a on:click|preventDefault={toggleDesktopFeatures} href="/#"
							>Features<span
								><img
									class:rotate-arrow={isDesktopFeaturesOpen ? 'rotate-arrow' : ''}
									src="icon-arrow-down.svg"
									alt="down arrow"
								/></span
							></a
						>
						{#if isDesktopFeaturesOpen}
							<ul
								transition:slide
								class:toggle-desktop-features={isDesktopFeaturesOpen
									? ''
									: 'toggle-desktop-features'}
							>
								<li>
									<span><img src="/icon-todo.svg" alt="Todo list" /></span><a href="/#">Todo List</a
									>
								</li>
								<li>
									<span><img src="/icon-calendar.svg" alt="Calendar" /></span><a href="/#"
										>Calendar</a
									>
								</li>
								<li>
									<span><img src="/icon-reminders.svg" alt="Reminders" /></span><a href="/#"
										>Reminders</a
									>
								</li>
								<li>
									<span><img src="/icon-planning.svg" alt="Planning" /></span><a href="/#"
										>Planning</a
									>
								</li>
							</ul>
						{/if}
					</li>
					<li class="company">
						<a on:click|preventDefault={toggleDesktopCompany} href="/#"
							>Company<span
								><img
									class:rotate-arrow={isDesktopCompanyOpen ? 'rotate-arrow' : ''}
									src="icon-arrow-down.svg"
									alt="down arrow"
								/></span
							></a
						>
						{#if isDesktopCompanyOpen}
							<ul
								transition:slide
								class:toggle-desktop-company={isDesktopCompanyOpen ? '' : 'toggle-desktop-company'}
							>
								<li>
									<a href="/#">Todo List</a>
								</li>
								<li>
									<a href="/#">History</a>
								</li>
								<li>
									<a href="/#">Our Team</a>
								</li>
								<li>
									<a href="/#">Blog</a>
								</li>
							</ul>
						{/if}
					</li>
					<li><a href="/#">Careers</a></li>
					<li><a href="/#">About</a></li>
				</ul>
				<ul>
					<li><a href="/#">Login</a></li>
					<button>Register</button>
				</ul>
			</nav>
		</div>

		<!-- Mobile nav -->
		{#if isMobileNavOpen}
			<nav
				transition:fly={{ x: 300, duration: 750, opacity: 1 }}
				class="nav-mobile"
				class:toggle-nav={isMobileNavOpen ? '' : 'toggle-nav'}
			>
				<button on:click|preventDefault={closeMobileNav} class="close-button">
					<img src="/icon-close-menu.svg" alt="close" />
				</button>
				<ul>
					<li class="features">
						<a on:click|preventDefault={toggleMobileFeatures} href="/#"
							>Features<span
								><img
									class:rotate-arrow={isMobileFeaturesOpen ? 'rotate-arrow' : ''}
									src="icon-arrow-down.svg"
									alt="down arrow"
								/></span
							></a
						>
						{#if isMobileFeaturesOpen}
							<ul
								transition:slide
								class:toggle-mobile-features={isMobileFeaturesOpen ? '' : 'toggle-mobile-features'}
							>
								<li>
									<span><img src="/icon-todo.svg" alt="Todo list" /></span><a href="/#">Todo List</a
									>
								</li>
								<li>
									<span><img src="/icon-calendar.svg" alt="Calendar" /></span><a href="/#"
										>Calendar</a
									>
								</li>
								<li>
									<span><img src="/icon-reminders.svg" alt="Reminders" /></span><a href="/#"
										>Reminders</a
									>
								</li>
								<li>
									<span><img src="/icon-planning.svg" alt="Planning" /></span><a href="/#"
										>Planning</a
									>
								</li>
							</ul>
						{/if}
					</li>
					<li class="company">
						<a on:click|preventDefault={toggleMobileCompany} href="/#"
							>Company<span
								><img
									class:rotate-arrow={isMobileCompanyOpen ? 'rotate-arrow' : ''}
									src="icon-arrow-down.svg"
									alt="down arrow"
								/></span
							></a
						>
						{#if isMobileCompanyOpen}
							<ul
								transition:slide
								class:toggle-mobile-company={isMobileCompanyOpen ? '' : 'toggle-mobile-company'}
							>
								<li><a href="/#">History</a></li>
								<li><a href="/#">Our Team</a></li>
								<li><a href="/#">Blog</a></li>
							</ul>
						{/if}
					</li>
					<li><a href="/#">Careers</a></li>
					<li><a href="/#">About</a></li>
				</ul>
			</nav>
		{/if}
	</div>
</header>

<style>
	header {
		padding: 1.5rem;
	}

	.nav-mobile {
		position: absolute;
		top: 0;
		right: 0;
		bottom: 0;
		width: 66%;
		background-color: var(--almost-white);
		padding: 1.5rem;
		z-index: 20;
	}

	.nav-desktop {
		display: none;
	}

	.close-button {
		display: block;
		margin-inline-start: auto;
		padding-block-end: 1.5rem;
	}

	.toggle-nav,
	.toggle-mobile-features,
	.toggle-mobile-company {
		display: none;
	}

	.nav-container {
		display: flex;
		align-items: center;
		justify-content: space-between;
		/* overflow: hidden; */
	}

	.nav-mobile ul {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
	}

	.nav-mobile li a {
		display: flex;
		align-items: center;
		gap: 1rem;
	}

	.nav-mobile .features ul,
	.nav-mobile .company ul {
		margin-block-start: 1rem;
		margin-inline-start: 1.5rem;
	}

	.nav-mobile .features ul li {
		display: grid;
		grid-template-columns: 1.75rem auto;
	}

	.rotate-arrow {
		transform: rotateZ(180deg);
		transition: transform 0.5s;
	}

	@media (min-width: 768px) {
		header {
			padding: 2rem;
			max-width: 94rem;
			margin-inline: auto;
		}

		.button-mobile-nav,
		.nav-mobile {
			display: none;
		}

		.nav-container {
			display: flex;
			justify-content: space-between;
			align-items: center;
			gap: 4rem;
		}

		.nav-desktop,
		.nav-desktop ul {
			display: flex;
			align-items: center;
		}

		.nav-desktop {
			width: 100%;
			justify-content: space-between;
			align-items: center;
		}

		.nav-desktop ul {
			gap: 3rem;
		}

		.nav-desktop li a:hover {
			color: black;
		}

		.nav-desktop ul:nth-of-type(2) button {
			padding-inline: 2rem;
			padding-block: 1rem;
			border-radius: 1rem;
			border: 1px solid var(--medium-gray);
			font-family: var(--font-family);
		}

		.nav-desktop ul:nth-of-type(2) button:hover {
			border: 1px solid black;
		}

		.nav-desktop img {
			margin-inline-start: 0.5rem;
		}

		.nav-desktop .features,
		.nav-desktop .company {
			position: relative;
		}

		.nav-desktop .features ul,
		.nav-desktop .company ul {
			position: absolute;
			top: 2rem;
			right: 0;
			background-color: white;
			padding: 1rem;
			display: flex;
			flex-direction: column;
			align-items: start;
			gap: 1rem;
			border-radius: 1rem;
			box-shadow: 0px 24px 40px -24px rgba(0, 0, 0, 0.75);
			-webkit-box-shadow: 0px 24px 40px -24px rgba(0, 0, 0, 0.75);
			-moz-box-shadow: 0px 24px 40px -24px rgba(0, 0, 0, 0.75);
		}

		.nav-desktop .features ul li {
			display: grid;
			grid-template-columns: 1.5rem 1fr;
			gap: 1rem;
		}

		.nav-desktop .company ul li {
			width: max-content;
		}

		.toggle-desktop-features,
		.toggle-desktop-company {
			visibility: hidden;
		}
	}
</style>
