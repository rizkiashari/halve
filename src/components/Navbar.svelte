<script>
	import { onMount } from 'svelte';
	import { page } from '$app/stores';

	const showNavbar = () => {
		const navbar = document.getElementById('navbar-all');
		navbar.classList.toggle('is-active');
	};

	let currentUrl = '';

	onMount(() => {
		document.querySelector('.desktop-tr').addEventListener('click', function (event) {
			event.stopPropagation();
			this.classList.toggle('is-active');
		});
		document.querySelector('.mobile-tr').addEventListener('click', function (event) {
			event.stopPropagation();
			this.classList.toggle('is-active');
		});
	});

	$: {
		currentUrl = $page.url.href;
	}
</script>

<nav class="navbar is-fixed-top shadow" ariaRole="navigation" aria-label="main navigation">
	<div class="container">
		<div class="navbar-brand flex">
			<button class="navbar-burger" on:click={showNavbar}>
				<span aria-hidden="true" />
				<span aria-hidden="true" />
				<span aria-hidden="true" />
			</button>
			<a class="navbar-item" href="/">
				<img src="/icons/logo_halve.png" alt="Halve" class="logo image" />
			</a>
			<div class="dropdown mobile-tr navbar-item">
				<div class="dropdown-trigger">
					<button
						class="button is-white down-translate"
						aria-haspopup="true"
						aria-controls="dropdown-menu"
					>
						<img src="/icons/id.png" alt="flag en" class="icon-flag" />
						<p>ID</p>
						<span class="icon is-small">
							<i class="fa fa-angle-down" aria-hidden="true" />
						</span>
					</button>
				</div>
				<div class="dropdown-menu" id="dropdown-menu" role="menu">
					<div class="dropdown-content">
						<button class="button is-white dropdown-item content-flag">
							<img src="/icons/id.png" alt="flag en" class="icon-flag" />
							<p>ID</p>
						</button>
						<button class="button is-white dropdown-item content-flag">
							<img src="/icons/en.png" alt="flag en" class="icon-flag" />
							<p>EN</p>
						</button>
					</div>
				</div>
			</div>
		</div>

		<div id="navbar-all" class="navbar-menu">
			<div class="navbar-end">
				<a
					class="navbar-item {currentUrl.split('#')[1] === undefined ? 'active-nav' : ''}"
					href="/"
				>
					Home
				</a>
				<a
					class="navbar-item {currentUrl.split('#')[1] === 'how-it' ? 'active-nav' : ''}"
					href="#how-it"
				>
					How it Work
				</a>
				<a
					class="navbar-item {currentUrl.split('#')[1] === 'about-us' ? 'active-nav' : ''}"
					href="#about-us"
				>
					About Us
				</a>
				<a
					class="navbar-item {currentUrl.split('#')[1] === 'services' ? 'active-nav' : ''}"
					href="#services"
				>
					Services
				</a>
				<a
					class="navbar-item {currentUrl.split('#')[1] === 'volunteer' ? 'active-nav' : ''}"
					href="#volunteer"
				>
					Volunteer
				</a>
				<a
					class="navbar-item {currentUrl.split('#')[1] === 'contact-us' ? 'active-nav' : ''}"
					href="#contact-us"
				>
					Contact Us
				</a>
				<div class="dropdown desktop-tr navbar-item">
					<div class="dropdown-trigger">
						<button
							class="button is-white down-translate"
							aria-haspopup="true"
							aria-controls="dropdown-menu"
						>
							<img src="/icons/id.png" alt="flag en" class="icon-flag" />
							<p>ID</p>
							<span class="icon is-small">
								<i class="fa fa-angle-down" aria-hidden="true" />
							</span>
						</button>
					</div>
					<div class="dropdown-menu" id="dropdown-menu" role="menu">
						<div class="dropdown-content">
							<button class="button is-white dropdown-item content-flag">
								<img src="/icons/id.png" alt="flag en" class="icon-flag" />
								<p>ID</p>
							</button>
							<button class="button is-white dropdown-item content-flag">
								<img src="/icons/en.png" alt="flag en" class="icon-flag" />
								<p>EN</p>
							</button>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</nav>

<style>
	.logo {
		width: 5rem;
		height: 2rem;
		object-fit: cover;
		margin-top: 0.5rem;
	}

	.navbar-end {
		gap: 1rem;
	}

	.shadow {
		filter: drop-shadow(0px 4px 30px rgba(0, 0, 0, 0.05));
		margin-bottom: 2rem;
	}

	.navbar-burger {
		color: #add66b;
		margin: 0;
	}

	.dropdown-menu {
		min-width: 1rem;
	}

	.icon-flag {
		width: 2.2rem;
		height: 1.2rem;
	}

	.down-translate {
		display: flex;
		align-items: center;
	}
	.down-translate > p {
		margin-left: 0.5rem;
		color: #add66b;
	}

	.content-flag {
		display: flex;
		align-items: center;
		gap: 1rem;
		color: #add66b;
		font-size: 1rem;
	}

	.mobile-tr {
		display: none;
	}

	.active-nav {
		color: #add66b;
		border-bottom: 1px solid #add66b;
	}

	@media screen and (max-width: 1023px) {
		.flex {
			display: flex;
			justify-content: space-between;
		}
		.dropdown-menu {
			margin-right: 1rem;
		}
		.mobile-tr {
			display: block;
		}
		.desktop-tr {
			display: none;
		}

		.navbar-item {
			padding: 0.5rem 0 0.4rem;
			max-width: fit-content;
			margin-left: 1rem;
		}
	}
</style>
