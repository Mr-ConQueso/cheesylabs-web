<script lang="ts">
	import Navbar from '$lib/components/navigation/Navbar.svelte';
	import Window from '$lib/components/windows/Window.svelte';
	import Title from '$lib/components/generic/Title.svelte';
	import Button from '$lib/components/generic/Button.svelte';
	import Section from '$lib/components/generic/Section.svelte';
	import Footer from '$lib/components/navigation/Footer.svelte';

	const features = [
		{
			title: 'Videogames',
			icon: '🕹️',
			desc: 'Rubber-hose adventures with pixel-perfect physics.'
		},
		{
			title: 'Interactive',
			icon: '✨',
			desc: 'Web experiences that break the fourth wall.'
		},
		{
			title: 'Websites',
			icon: '🌐',
			desc: 'Retro-futuristic layouts built for modern engines.'
		},
		{
			title: 'Mobile Apps',
			icon: '📱',
			desc: 'Pocket-sized fun with buttery smooth UI.'
		}
	];

	const projects = [
		{
			title: 'Flight X08',
			category: 'Game Dev',
			desc: 'The last journey for people who want to escape AI.',
			color: 'var(--primary)'
		},
		{
			title: 'Leenzy Adventure',
			category: 'Interactive',
			desc: 'A core adventure to save the world.',
			color: 'var(--secondary)'
		},
		{
			title: 'The Algorithm',
			category: 'Web App',
			desc: 'Do you want to be cool for $29.99?',
			color: 'var(--pink)'
		}
	];
</script>

<Navbar />

<main class="page-container">
	<!-- ============================= -->
	<!--          HERO SECTION         -->
	<!-- ============================= -->
	<header class="hero-section">
		<div class="hero-grid">
			<div class="hero-content">
				<!-- Rotated window for "tossed on desk" feel -->
				<Window title="System_Boot.exe" style="transform: rotate(-1.5deg);">
					<Title level={1}>We Cook <span class="highlight">Delicious</span> Digital Products.</Title>
					<p class="hero-text">
						<strong>Cheesy Labs</strong> is a rubber-hose retro studio crafting videogames,
						websites, and interactive media that stick to your memory.
					</p>
					<div class="hero-actions">
						<Button href="#contact">Start Project</Button>
						<a href="#portfolio" class="link-secondary">View Works</a>
					</div>
				</Window>
			</div>

			<div class="hero-visual">
				<div class="stack-wrapper">
					<!-- Visual Backing for depth -->
					<div class="visual-back"></div>
					<Window title="Preview.bmp" style="background: var(--light);">
						<div class="placeholder-art">
							<div class="cheese-wedge">🧀</div>
							<h3>Mr. ConQueso</h3>
							<p>Status: Online</p>
						</div>
					</Window>
				</div>
			</div>
		</div>
	</header>

	<!-- ============================= -->
	<!--        FEATURES SECTION       -->
	<!-- ============================= -->
	<Section title="Our Ingredients">
		<div id="services" class="grid-4">
			{#each features as feature}
				<div class="feature-card">
					<div class="feature-icon-wrapper">
						<span class="feature-icon">{feature.icon}</span>
					</div>
					<h3 class="feature-title">{feature.title}</h3>
					<p>{feature.desc}</p>
				</div>
			{/each}
		</div>
	</Section>

	<!-- ============================= -->
	<!--          ABOUT SECTION        -->
	<!-- ============================= -->
	<Section title="The Lab">
		<div id="about" class="about-grid">
			<Window title="Manifesto.txt">
				<div class="terminal-text">
					<p>> LOADING CREATIVITY... 100%</p>
					<p>> INSERTING SOUL... DONE</p>
					<br>
					<p>
						Cheesy Labs was founded with a simple mission: <strong>Make the internet fun again.</strong>
					</p>
					<p>
						We ditch sterile minimalism for bold borders, chunky fonts, and experiences
						that feel like finding a hidden level in your favorite game.
					</p>
				</div>
			</Window>

			<div class="about-visual">
				<!-- Stickers using Brand Colors -->
				<div class="sticker sticker-1">Build</div>
				<div class="sticker sticker-2">Play</div>
				<div class="sticker sticker-3">Create</div>
			</div>
		</div>
	</Section>

	<!-- ============================= -->
	<!--        PORTFOLIO SECTION      -->
	<!-- ============================= -->
	<Section title="Selected Works">
		<div id="portfolio" class="grid-3">
			{#each projects as project}
				<div class="project-wrapper">
					<Window title={project.category} style="margin: 0; height: 100%; display: flex; flex-direction: column;">
						<div class="project-preview" style="background-color: {project.color};">
							<span class="project-emoji">📂</span>
						</div>
						<div class="project-info">
							<h3 class="project-title">{project.title}</h3>
							<p class="project-desc">{project.desc}</p>
							<div class="mt-auto">
								<Button href="#">View Case</Button>
							</div>
						</div>
					</Window>
				</div>
			{/each}
		</div>
	</Section>

	<!-- ============================= -->
	<!--      TESTIMONIAL SECTION      -->
	<!-- ============================= -->
	<Section title="Lab Reports">
		<div class="testimonial-container">
			<Window title="Review.msg">
				<div class="quote-block">
					<span class="quote-mark">“</span>
					<p class="quote-text">
						Cheesy Labs didn't just build our website, they built a time machine.
						It's the most distinct digital presence we've ever had.
					</p>
					<div class="quote-author">
						<div class="author-avatar"></div>
						<div>
							<strong>Sarah Jenkins</strong>
							<span class="author-role">CEO, RetroTech</span>
						</div>
					</div>
				</div>
			</Window>
		</div>
	</Section>

	<!-- ============================= -->
	<!--          CTA SECTION          -->
	<!-- ============================= -->
	<Section title="Start Game">
		<div id="contact" class="cta-grid">
			<div class="cta-form-wrapper">
				<Window title="Contact_Form.exe" style="background: var(--primary);">
					<form class="contact-form" onsubmit={(e) => e.preventDefault()}>
						<div class="form-group">
							<label for="name">Player Name</label>
							<input type="text" id="name" placeholder="Enter your name" />
						</div>
						<div class="form-group">
							<label for="quest">Quest Type</label>
							<select id="quest">
								<option>New Website</option>
								<option>Mobile App</option>
								<option>Game Development</option>
								<option>Just saying hi!</option>
							</select>
						</div>
						<div class="form-group">
							<label for="message">Message</label>
							<textarea id="message" rows="3" placeholder="Tell us about your project..."></textarea>
						</div>
						<Button style="width: 100%; justify-content: center;">Send It ➜</Button>
					</form>
				</Window>
			</div>

			<div class="cta-info">
				<Window title="Info.txt" style="height: fit-content;">
					<h3>Contact Details</h3>
					<ul class="info-list">
						<li>📧 hello@cheesylabs.com</li>
						<li>📞 +1 (555) 123-4567</li>
						<li>📍 Madrid, Spain</li>
					</ul>
					<hr class="dashed-line" />
					<p class="small-print">
						* No actual cheese is sent via email.
					</p>
				</Window>
			</div>
		</div>
	</Section>
</main>

<Footer />

<style>
    /* --- Global Layout --- */
    .page-container {
        max-width: 1100px;
        margin: 0 auto;
        padding: 0 1.5rem;
        overflow-x: hidden; /* Hide overflow from rotated elements */
    }

    .highlight {
        color: var(--primary);
    }

    /* --- Hero --- */
    .hero-section {
        padding: 4rem 0;
    }

    .hero-grid {
        display: grid;
        grid-template-columns: 1fr;
        gap: 3rem;
        align-items: center;
    }

    .hero-text {
        font-size: 1.25rem;
        line-height: 1.6;
        margin-bottom: 2rem;
        color: var(--dark);
    }

    .hero-actions {
        display: flex;
        gap: 1.5rem;
        align-items: center;
    }

    .link-secondary {
        font-family: var(--font-h1);
        color: var(--dark);
        text-decoration: underline;
        text-decoration-thickness: 2px;
        text-underline-offset: 4px;
        cursor: pointer;
    }

    .link-secondary:hover {
        color: var(--primary);
    }

    .stack-wrapper {
        position: relative;
        padding: 1rem;
    }

    .visual-back {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        background: var(--darkgreen);
        border: var(--border-big);
        border-radius: var(--radius);
        transform: rotate(3deg);
        z-index: -1;
        box-shadow: var(--shadow-big);
    }

    .placeholder-art {
        height: 300px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
        background-image: radial-gradient(var(--primary) 15%, transparent 16%);
        background-size: 16px 16px;
    }

    .cheese-wedge {
        font-size: 5rem;
        margin-bottom: 1rem;
        animation: float 3s ease-in-out infinite;
    }

    /* --- Features --- */
    .grid-4 {
        display: grid;
        gap: 2rem;
        grid-template-columns: 1fr;
    }

    .feature-card {
        background: var(--background);
        border: var(--border-big);
        border-radius: var(--radius);
        padding: 2rem;
        text-align: center;
        box-shadow: var(--shadow-small);
        transition: transform 0.2s;
    }

    .feature-card:hover {
        transform: translateY(-5px);
        box-shadow: var(--shadow-medium);
    }

    .feature-icon-wrapper {
        width: 60px;
        height: 60px;
        margin: 0 auto 1rem auto;
        background: var(--light);
        border: var(--border-small);
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .feature-icon {
        font-size: 2rem;
    }

    .feature-title {
        font-family: var(--font-h1);
        color: var(--primary);
        font-size: 1.4rem;
        margin-bottom: 0.5rem;
    }

    /* --- About --- */
    .about-grid {
        display: grid;
        gap: 3rem;
        grid-template-columns: 1fr;
    }

    .terminal-text {
        font-family: "Courier New", monospace;
        font-weight: bold;
    }

    .about-visual {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 1rem;
        min-height: 200px;
    }

    .sticker {
        padding: 1rem 2rem;
        border: var(--border-big);
        border-radius: 50%;
        font-family: var(--font-h1);
        font-size: 1.5rem;
        box-shadow: var(--shadow-small);
    }

    .sticker-1 { background: var(--primary); color: white; transform: rotate(-10deg); }
    .sticker-2 { background: var(--pink); color: var(--dark); transform: rotate(5deg); z-index: 2; }
    .sticker-3 { background: var(--secondary); color: white; transform: rotate(-5deg); }

    /* --- Portfolio --- */
    .grid-3 {
        display: grid;
        gap: 2rem;
        grid-template-columns: 1fr;
    }

    .project-wrapper {
        height: 100%;
    }

    .project-preview {
        height: 180px;
        border: var(--border-small);
        margin-bottom: 1rem;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 8px;
    }

    .project-emoji {
        font-size: 3rem;
    }

    .project-info {
        flex-grow: 1;
        display: flex;
        flex-direction: column;
    }

    .project-title {
        font-family: var(--font-h1);
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
    }

    .project-desc {
        margin-bottom: 1.5rem;
        font-size: 0.95rem;
    }

    .mt-auto {
        margin-top: auto;
    }

    /* --- Testimonial --- */
    .testimonial-container {
        max-width: 800px;
        margin: 0 auto;
    }

    .quote-block {
        text-align: center;
        padding: 1rem;
    }

    .quote-mark {
        display: block;
        font-family: var(--font-h1);
        font-size: 4rem;
        line-height: 0.5;
        color: var(--primary);
        margin-bottom: 1rem;
    }

    .quote-text {
        font-size: 1.2rem;
        font-style: italic;
        margin-bottom: 2rem;
    }

    .quote-author {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 1rem;
        text-align: left;
    }

    .author-avatar {
        width: 50px;
        height: 50px;
        background: var(--pink);
        border: var(--border-small);
        border-radius: 50%;
    }

    .author-role {
        display: block;
        font-size: 0.85rem;
        opacity: 0.7;
        text-transform: uppercase;
        font-weight: bold;
    }

    /* --- CTA --- */
    .cta-grid {
        display: grid;
        gap: 2rem;
        grid-template-columns: 1fr;
    }

    .contact-form {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }

    .form-group label {
        display: block;
        font-family: var(--font-h1);
        font-size: 0.9rem;
        margin-bottom: 0.5rem;
        color: var(--dark);
    }

    .form-group input,
    .form-group select,
    .form-group textarea {
        width: 100%;
        padding: 0.8rem;
        border: var(--border-small);
        border-radius: 8px;
        background: var(--light);
        font-family: var(--font-body);
        font-size: 1rem;
        box-sizing: border-box;
    }

    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus {
        outline: none;
        border-color: var(--dark);
        box-shadow: 2px 2px 0 var(--dark);
    }

    .info-list {
        list-style: none;
        padding: 0;
        margin: 1.5rem 0;
        font-size: 1.1rem;
        line-height: 2;
    }

    .dashed-line {
        border: none;
        border-top: 2px dashed var(--dark);
        margin: 1.5rem 0;
        opacity: 0.3;
    }

    .small-print {
        font-size: 0.8rem;
        font-style: italic;
        opacity: 0.6;
    }

    /* --- Animations --- */
    @keyframes float {
        0%, 100% { transform: translateY(0); }
        50% { transform: translateY(-10px); }
    }

    /* --- Responsive --- */
    @media (min-width: 768px) {
        .hero-grid {
            grid-template-columns: 1.1fr 0.9fr;
        }

        .grid-4 {
            grid-template-columns: repeat(2, 1fr);
        }

        .grid-3 {
            grid-template-columns: repeat(3, 1fr);
        }

        .about-grid {
            grid-template-columns: 1.5fr 1fr;
        }

        .cta-grid {
            grid-template-columns: 1.5fr 1fr;
        }
    }

    @media (min-width: 1024px) {
        .grid-4 {
            grid-template-columns: repeat(4, 1fr);
        }
    }
</style>