<script lang="ts">
	import Title from '$lib/components/generic/Title.svelte';
	import Window from '$lib/components/windows/Window.svelte';
	import Section from '$lib/components/generic/Section.svelte';
	import Button from '$lib/components/generic/Button.svelte';

	const projects = [
		{
			id: "flight-x08",
			title: "Flight X08",
			category: "Game Dev",
			desc: "A narrative-driven survival game about the last journey for humanity escaping AI. Features retro-3D aesthetics mixed with 2D rubber-hose characters.",
			tags: ["Unity", "C#", "Pixel Art"],
			color: "var(--primary)",
			icon: "✈️"
		},
		{
			id: "leenzy",
			title: "Leenzy Adventure",
			category: "Interactive Web",
			desc: "A promotional interactive website for a birthday event turned into an RPG. Users navigate a map to unlock real-world rewards.",
			tags: ["Svelte", "Three.js", "Illustration"],
			color: "var(--secondary)",
			icon: "🗺️"
		},
		{
			id: "algorithm",
			title: "The Algorithm",
			category: "Web App",
			desc: "A satirical e-commerce experience that guarantees 'coolness' for $29.99. A commentary on influencer culture wrapped in a 90s OS interface.",
			tags: ["React", "Stripe", "Satire"],
			color: "var(--pink)",
			icon: "💾"
		},
		{
			id: "macindows",
			title: "Macindows Template",
			category: "Design System",
			desc: "The very design system you are looking at! A brutalist, retro-OS styled UI kit for Svelte and Webflow.",
			tags: ["UI/UX", "Open Source", "Cheese"],
			color: "var(--light)",
			icon: "🖥️"
		}
	];

	// --- Archive / Prototypes Data ---
	const archive = [
		{ name: "proto_physics_test_v4.exe", date: "2024-11-02", size: "12MB" },
		{ name: "cheese_shader_final_FINAL.glsl", date: "2024-10-15", size: "4KB" },
		{ name: "rubber_hose_rig.blend", date: "2024-09-28", size: "145MB" },
		{ name: "secret_level_design.png", date: "2024-08-10", size: "2.4MB" }
	];
</script>

<main class="page-container">
	<!-- ============================= -->
	<!--          HERO HEADER          -->
	<!-- ============================= -->
	<header class="portfolio-header">
		<div class="header-content">
			<Title level={1}>The Lab <span class="highlight">Archives.</span></Title>
			<p class="intro-text">
				A collection of our finest digital experiments. Some are games, some are websites,
				and some are just excuses to make things bounce.
			</p>
		</div>

		<!-- Decorative "Floppy Disk" Window -->
		<div class="header-decoration">
			<Window title="A:/" style="transform: rotate(3deg); max-width: 300px; margin: 0 auto;">
				<div class="disk-label">
					<span>CONFIDENTIAL</span>
					<strong>DO NOT COPY</strong>
				</div>
				<div class="disk-shutter"></div>
			</Window>
		</div>
	</header>

	<!-- ============================= -->
	<!--       FEATURED PROJECTS       -->
	<!-- ============================= -->
	<Section title="Featured Works">
		<div class="projects-grid">
			{#each projects as project}
				<div class="project-card">
					<Window title={project.category} style="height: 100%; display: flex; flex-direction: column; margin: 0;">
						<!-- Visual Preview Box -->
						<div class="project-visual" style="background-color: {project.color};">
							<span class="visual-icon">{project.icon}</span>
							<div class="visual-overlay"></div>
						</div>

						<div class="project-body">
							<h3 class="project-title">{project.title}</h3>

							<div class="tags-container">
								{#each project.tags as tag}
									<span class="tag">{tag}</span>
								{/each}
							</div>

							<p class="project-desc">{project.desc}</p>

							<div class="project-actions">
								<Button href="/projects/{project.id}">View Case Study</Button>
								<span class="file-info">SIZE: 24MB</span>
							</div>
						</div>
					</Window>
				</div>
			{/each}
		</div>
	</Section>

	<!-- ============================= -->
	<!--       ARCHIVE / LIST          -->
	<!-- ============================= -->
	<Section title="Prototype Bin">
		<Window title="C:\Users\MrConQueso\Downloads">
			<div class="file-list">
				<div class="file-header">
					<span>Name</span>
					<span class="hide-mobile">Date Modified</span>
					<span>Size</span>
					<span>Action</span>
				</div>
				{#each archive as file}
					<div class="file-row">
						<div class="file-name">
							<span class="file-icon">📄</span>
							{file.name}
						</div>
						<div class="file-date hide-mobile">{file.date}</div>
						<div class="file-size">{file.size}</div>
						<div class="file-action">
							<button class="download-btn">⬇</button>
						</div>
					</div>
				{/each}
			</div>
		</Window>
	</Section>

	<!-- ============================= -->
	<!--           CTA                 -->
	<!-- ============================= -->
	<div class="cta-wrapper">
		<Section title="Got a Crazy Idea?">
			<div class="cta-box">
				<p>We love turning weird concepts into shipped software.</p>
				<Button href="/#contact">Start Project</Button>
			</div>
		</Section>
	</div>

</main>

<style>
    /* --- Layout --- */
    .page-container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 0 1.5rem;
        overflow-x: hidden;
    }

    .highlight {
        color: var(--primary);
    }

    /* --- Header --- */
    .portfolio-header {
        padding: 4rem 0;
        text-align: center;
        display: flex;
        flex-direction: column;
        gap: 2rem;
    }

    .intro-text {
        font-size: 1.2rem;
        max-width: 600px;
        margin: 1rem auto;
        color: var(--dark);
    }

    .disk-label {
        background: #eee;
        padding: 1rem;
        border: 2px solid #ccc;
        text-align: center;
        font-family: "Courier New", monospace;
        display: flex;
        flex-direction: column;
        border-radius: 4px;
    }

    .disk-label strong {
        color: red;
        font-size: 1.2rem;
        display: block;
        margin-top: 0.5rem;
        transform: rotate(-5deg);
        border: 2px solid red;
        padding: 0.2rem;
    }

    .disk-shutter {
        height: 40px;
        background: silver;
        margin-top: 1rem;
        border: 2px solid gray;
        border-radius: 4px;
    }

    /* --- Projects Grid --- */
    .projects-grid {
        display: grid;
        grid-template-columns: 1fr;
        gap: 2rem;
    }

    .project-card {
        height: 100%;
    }

    .project-visual {
        height: 200px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-bottom: var(--border-big);
        position: relative;
        overflow: hidden;
    }

    .visual-icon {
        font-size: 5rem;
        z-index: 1;
        transition: transform 0.3s ease;
    }

    .project-card:hover .visual-icon {
        transform: scale(1.2) rotate(5deg);
    }

    .visual-overlay {
        position: absolute;
        top: 0; left: 0; right: 0; bottom: 0;
        background-image: radial-gradient(rgba(0,0,0,0.1) 15%, transparent 16%);
        background-size: 8px 8px;
    }

    .project-body {
        padding: 0;
        flex-grow: 1;
        display: flex;
        flex-direction: column;
    }

    .project-title {
        font-family: var(--font-h1);
        font-size: 1.8rem;
        margin-bottom: 0.5rem;
        color: var(--dark);
    }

    .tags-container {
        display: flex;
        gap: 0.5rem;
        flex-wrap: wrap;
        margin-bottom: 1rem;
    }

    .tag {
        font-size: 0.8rem;
        font-weight: bold;
        text-transform: uppercase;
        background: var(--dark);
        color: var(--light);
        padding: 0.2rem 0.6rem;
        border-radius: 4px;
    }

    .project-desc {
        margin-bottom: 1.5rem;
        line-height: 1.5;
        opacity: 0.9;
    }

    .project-actions {
        margin-top: auto;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .file-info {
        font-family: "Courier New", monospace;
        font-size: 0.8rem;
        opacity: 0.6;
        font-weight: bold;
    }

    /* --- Archive List --- */
    .file-list {
        font-family: "Courier New", monospace;
    }

    .file-header {
        display: grid;
        grid-template-columns: 2fr 1fr 100px 50px;
        padding: 0.5rem;
        border-bottom: 2px solid var(--dark);
        font-weight: bold;
        text-transform: uppercase;
        background: #eee;
    }

    .file-row {
        display: grid;
        grid-template-columns: 2fr 1fr 100px 50px;
        padding: 0.8rem 0.5rem;
        border-bottom: 1px solid #ddd;
        align-items: center;
        transition: background 0.1s;
    }

    .file-row:hover {
        background: var(--light);
        cursor: pointer;
    }

    .file-name {
        font-weight: bold;
        display: flex;
        align-items: center;
        gap: 0.5rem;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }

    .download-btn {
        background: none;
        border: none;
        cursor: pointer;
        font-size: 1.2rem;
        color: var(--primary);
    }

    .download-btn:hover {
        transform: translateY(2px);
    }

    /* --- CTA --- */
    .cta-wrapper {
        text-align: center;
    }

    .cta-box {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1rem;
    }

    /* --- Responsive --- */
    @media (max-width: 768px) {
        .hide-mobile {
            display: none;
        }

        .file-header, .file-row {
            grid-template-columns: 1fr 80px 50px; /* Adjusted for mobile */
        }
    }

    @media (min-width: 768px) {
        .projects-grid {
            grid-template-columns: 1fr 1fr;
        }

        .portfolio-header {
            flex-direction: row;
            align-items: center;
            justify-content: space-between;
            text-align: left;
        }

        .intro-text {
            margin: 1rem 0;
        }
    }
</style>