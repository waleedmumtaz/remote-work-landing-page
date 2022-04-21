<script>
	import { isOverlayOpen } from '$lib/stores/OverlayStore.js';
	import { fly, slide } from 'svelte/transition';

	let isNavOpen = false;
	let isFeaturesOpen = false;
	let isCompanyOpen = false;

	const openNav = () => {
		isNavOpen = true;
		isOverlayOpen.set(true);
	};

	const closeNav = () => {
		isNavOpen = false;
		isOverlayOpen.set(false);
	};

	const toggleFeatures = () => {
		isFeaturesOpen = !isFeaturesOpen;
	};

	const toggleCompany = () => {
		isCompanyOpen = !isCompanyOpen;
	};
</script>

<header>
	<div>
		<div class="nav-mobile">
			<img src="/logo.svg" alt="logo" />
			<button on:click|preventDefault={openNav}>
				<img src="/icon-menu.svg" alt="menu" />
			</button>
		</div>
		{#if isNavOpen}
			<nav
				transition:fly={{ x: 300, duration: 750, opacity: 1 }}
				class:toggle-nav={isNavOpen ? '' : 'toggle-nav'}
			>
				<button on:click|preventDefault={closeNav} class="close-button">
					<img src="/icon-close-menu.svg" alt="close" />
				</button>
				<ul>
					<li class="features">
						<a on:click|preventDefault={toggleFeatures} href="/#"
							>Features<span
								><img
									class:rotate-arrow={isFeaturesOpen ? 'rotate-arrow' : ''}
									src="icon-arrow-down.svg"
									alt="down arrow"
								/></span
							></a
						>
						{#if isFeaturesOpen}
							<ul transition:slide class:toggle-features={isFeaturesOpen ? '' : 'toggle-features'}>
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
						<a on:click|preventDefault={toggleCompany} href="/#"
							>Company<span
								><img
									class:rotate-arrow={isCompanyOpen ? 'rotate-arrow' : ''}
									src="icon-arrow-down.svg"
									alt="down arrow"
								/></span
							></a
						>
						{#if isCompanyOpen}
							<ul transition:slide class:toggle-company={isCompanyOpen ? '' : 'toggle-company'}>
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
		padding: var(--size-5);
	}

	nav {
		position: absolute;
		top: 0;
		right: 0;
		bottom: 0;
		width: 66%;
		background-color: var(--almost-white);
		padding: var(--size-5);
		z-index: 20;
	}

	.close-button {
		display: block;
		margin-inline-start: auto;
		padding-block-end: var(--size-5);
	}

	.toggle-nav,
	.toggle-features,
	.toggle-company {
		display: none;
	}

	.nav-mobile {
		display: flex;
		align-items: center;
		justify-content: space-between;
		overflow: hidden;
	}

	ul {
		display: flex;
		flex-direction: column;
		gap: var(--size-5);
	}

	li a {
		display: flex;
		align-items: center;
		gap: var(--size-3);
	}

	.features ul,
	.company ul {
		margin-block-start: var(--size-3);
		margin-inline-start: var(--size-5);
	}

	.features ul li {
		display: grid;
		grid-template-columns: var(--size-6) auto;
	}

	.rotate-arrow {
		transform: rotateZ(180deg);
		transition: transform 0.5s;
	}
</style>
