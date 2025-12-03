<script lang="ts">
	const year = new Date().getFullYear();
</script>

<footer class="footer">
	<div class="container">
		<div class="col">
			<h3 class="footer-title">Cheesy Labs</h3>
			<p>Cooking up digital delight since 2023.</p>
			<p>© {year} Cheesy Labs Inc.</p>
		</div>
		<div class="col">
			<h4 class="footer-head">Sitemap</h4>
			<a href="/#">Home</a>
			<a href="/#services">Services</a>
			<a href="/about">About</a>
			<a href="/portfolio">Work</a>
			<a href="/#contact">Contact</a>
		</div>
		<div class="col">
			<h4 class="footer-head">Socials</h4>
			<a href="#">Twitter / X</a>
			<a href="#">Instagram</a>
			<a href="#">LinkedIn</a>
		</div>
	</div>
</footer>

<style>
    .footer {
        margin-top: 4rem;
        border-top: var(--border-big);
        background: var(--dark);
        color: var(--light);
        padding: 4rem 1.5rem;
        font-family: var(--font-body);
    }

    .container {
        max-width: 1200px;
        margin: 0 auto;
        display: grid;
        gap: 2rem;
        grid-template-columns: 1fr;
    }

    .footer-title {
        font-family: var(--font-h1);
        color: var(--primary);
        font-size: 2rem;
        margin-bottom: 1rem;
    }

    .footer-head {
        font-family: var(--font-h1);
        color: var(--pink);
        font-size: 1.2rem;
        margin-bottom: 1rem;
        text-transform: uppercase;
    }

    a {
        display: block;
        color: var(--light);
        text-decoration: none;
        margin-bottom: 0.5rem;
        opacity: 0.8;
    }

    a:hover {
        opacity: 1;
        color: var(--primary);
    }

    @media (min-width: 768px) {
        .container {
            grid-template-columns: 2fr 1fr 1fr;
        }
    }
</style>