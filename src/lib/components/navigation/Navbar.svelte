<script lang="ts">
	let isMenuOpen = $state(false);

	function toggleMenu() {
		isMenuOpen = !isMenuOpen;
	}

	const sitemap = [
		{ name: "Services", href: "/#services" },
		{ name: "About", href: "/about" },
		{ name: "Work", href: "/portfolio" },
		{ name: "Contact", href: "/#contact" }
	];
</script>

<nav class="navbar">
	<div class="nav-container">
		<!-- Logo Section -->
		<a href="/" class="brand">
			<img class="logo" src="/icons/favicon.svg" alt="Logo" />
			<span class="brand-name">Cheesy Labs</span>
		</a>

		<!-- Desktop Links -->
		<div class="desktop-links">
			{#each sitemap as link}
				<a href={link.href}>{link.name}</a>
			{/each}
		</div>

		<!-- Mobile Toggle -->
		<button class="menu-toggle" onclick={toggleMenu} aria-label="Toggle Menu">
			☰
		</button>
	</div>

	<!-- Mobile Menu (Dropdown) -->
	{#if isMenuOpen}
		<div class="mobile-menu">
			{#each sitemap as link}
				<a href={link.href} onclick={() => (isMenuOpen = false)}>{link.name}</a>
			{/each}
		</div>
	{/if}
</nav>

<style>
    .navbar {
        position: sticky;
        top: 0;
        z-index: 1000;
        background: var(--light);
        border-bottom: var(--border-big);
        padding: 1rem 0;
    }

    .nav-container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 0 1.5rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .brand {
        display: flex;
        align-items: center;
        gap: 0.8rem;
        text-decoration: none;
        color: var(--dark);
    }

		.logo {
        width: 40px;
        height: 40px;
		}

    .brand-name {
        font-family: var(--font-h1);
        font-size: 1.5rem;
    }

    .desktop-links {
        display: none;
        gap: 2rem;
    }

    .desktop-links a {
        font-family: var(--font-body);
        font-weight: 700;
        text-transform: uppercase;
        text-decoration: none;
        color: var(--dark);
        transition: color 0.2s;
    }

    .desktop-links a:hover {
        color: var(--primary);
        text-decoration: underline;
        text-decoration-thickness: 3px;
    }

    .menu-toggle {
        display: block;
        background: none;
        border: var(--border-small);
        font-size: 1.5rem;
        cursor: pointer;
        padding: 0.2rem 0.6rem;
        border-radius: 8px;
        box-shadow: var(--shadow-small);
    }

    .mobile-menu {
        background: var(--primary);
        border-bottom: var(--border-big);
        padding: 1rem;
        display: flex;
        flex-direction: column;
        gap: 1rem;
        text-align: center;
    }

    .mobile-menu a {
        font-family: var(--font-h1);
        font-size: 1.5rem;
        color: var(--dark);
        text-decoration: none;
    }

    @media (min-width: 768px) {
        .desktop-links {
            display: flex;
        }
        .menu-toggle {
            display: none;
        }
    }
</style>