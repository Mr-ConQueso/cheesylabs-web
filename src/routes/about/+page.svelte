<script lang="ts">
	import Title from '$lib/components/generic/Title.svelte';
	import Window from '$lib/components/windows/Window.svelte';
	import Section from '$lib/components/generic/Section.svelte';
	import Button from '$lib/components/generic/Button.svelte';

	const team = [
		{
			name: "Mr. ConQueso",
			role: "The Big Cheese",
			bio: "Founder, mascot, and chaotic good developer. He writes code with one hand and eats nachos with the other.",
			icon: "🧀",
			color: "var(--primary)"
		},
		{
			name: "Nini",
			role: "Lead Nap Engineer",
			bio: "Responsible for the 'N' in the logo and ensuring strict adherence to the 18-hour sleep schedule.",
			icon: "💤",
			color: "var(--pink)"
		},
		{
			name: "Cheddar Bot",
			role: "Automated Intern",
			bio: "A script that runs on a Raspberry Pi. It tries its best but sometimes deletes production.",
			icon: "🤖",
			color: "var(--secondary)"
		}
	];

	// --- Stats Data ---
	const stats = [
		{ label: "Lines of Code", value: "84,000+", change: "+12%" },
		{ label: "Coffees Consumed", value: "9,001", change: "+5%" },
		{ label: "Bugs 'Fixed'", value: "404", change: "0%" },
		{ label: "Cheese Rating", value: "11/10", change: "MAX" }
	];

	// --- FAQ Data ---
	const faqs = [
		{
			q: "Why 'Cheesy' Labs?",
			a: "Because software should be fun, flavorful, and sometimes a little messy. Also, we really like dairy products."
		},
		{
			q: "Do you only make games?",
			a: "Nope! We build websites, apps, and interactive experiences. If it runs on a screen and needs personality, we build it."
		},
		{
			q: "Is Mr. ConQueso a real person?",
			a: "Legally, we cannot confirm or deny if he is a human in a costume or a sentient piece of Gouda."
		}
	];
</script>

<main class="page-container">
	<!-- ============================= -->
	<!--       HEADER / MISSION        -->
	<!-- ============================= -->
	<header class="about-header">
		<div class="header-grid">
			<div class="header-text">
				<Title level={1}>Behind the <br><span class="highlight">Curtain.</span></Title>
				<p class="intro-text">
					We are a digital studio that refuses to be boring. In a world of sterile corporate
					memphis design, we choose <strong>chaos, charm, and rubber-hose physics.</strong>
				</p>
			</div>
			<div class="header-visual">
				<Window title="Mission_Statement.txt" style="transform: rotate(2deg);">
					<div class="console-text">
						<p>> INIT PROTOCOL: FUN</p>
						<p>> SET STYLE: 1920s_CARTOON</p>
						<p>> SET UI: RETRO_OS</p>
						<p>> EXECUTE...</p>
						<br>
						<p class="typing-cursor">_</p>
					</div>
				</Window>
			</div>
		</div>
	</header>

	<!-- ============================= -->
	<!--           STORY               -->
	<!-- ============================= -->
	<Section title="Our Story">
		<div class="story-container">
			<Window title="History.doc">
				<div class="story-content">
					<p>
						Founded in 2025, <strong>Cheesy Labs</strong> started as an extension of the personal brand
						of <em>Mr. ConQueso</em>. The goal was simple: bring the soul of early animation into
						modern web development.
					</p>
					<p>
						We believe that a website isn't just a container for information—it's a world.
						It should have its own logic, its own gravity, and yes, its own cheese.
						We specialize in <strong>"Macindows"</strong> aesthetics: bold borders, hard shadows,
						and UI elements that feel tactile.
					</p>
				</div>
			</Window>
		</div>
	</Section>

	<!-- ============================= -->
	<!--            TEAM               -->
	<!-- ============================= -->
	<Section title="The Crew">
		<div class="team-grid">
			{#each team as member}
				<div class="team-card-wrapper">
					<Window title={member.name} style="height: 100%; margin: 0;">
						<div class="team-avatar" style="background: {member.color}">
							<span class="avatar-icon">{member.icon}</span>
						</div>
						<div class="team-info">
							<h3 class="team-role">{member.role}</h3>
							<p class="team-bio">{member.bio}</p>
						</div>
					</Window>
				</div>
			{/each}
		</div>
	</Section>

	<!-- ============================= -->
	<!--            STATS              -->
	<!-- ============================= -->
	<Section title="System Monitor">
		<Window title="Task_Manager.exe" style="max-width: 800px; margin: 0 auto;">
			<div class="stats-grid">
				{#each stats as stat}
					<div class="stat-item">
						<span class="stat-label">{stat.label}</span>
						<span class="stat-value">{stat.value}</span>
						<span class="stat-change">{stat.change}</span>
					</div>
				{/each}
			</div>
			<div class="loading-bar-container">
				<span>System Load:</span>
				<div class="loading-bar">
					<div class="loading-progress"></div>
				</div>
			</div>
		</Window>
	</Section>

	<!-- ============================= -->
	<!--             FAQ               -->
	<!-- ============================= -->
	<Section title="Readme.txt">
		<div class="faq-grid">
			{#each faqs as faq}
				<Window title="Question?" style="margin: 0;">
					<h3 class="faq-question">{faq.q}</h3>
					<p class="faq-answer">{faq.a}</p>
				</Window>
			{/each}
		</div>
	</Section>

	<!-- ============================= -->
	<!--           CONTACT             -->
	<!-- ============================= -->
	<div class="cta-wrapper">
		<Section title="Ready to Join?">
			<div class="cta-box">
				<p>We are always looking for new players.</p>
				<Button href="/#contact">Contact Us</Button>
			</div>
		</Section>
	</div>
</main>

<style>
    /* --- Layout --- */
    .page-container {
        max-width: 1000px;
        margin: 0 auto;
        padding: 0 1.5rem;
        overflow-x: hidden;
    }

    .highlight {
        color: var(--primary);
    }

    /* --- Header --- */
    .about-header {
        padding: 6rem 0 4rem 0;
    }

    .header-grid {
        display: grid;
        grid-template-columns: 1fr;
        gap: 3rem;
        align-items: center;
    }

    .intro-text {
        font-size: 1.2rem;
        line-height: 1.6;
        margin-top: 1rem;
        color: var(--dark);
    }

    .console-text {
        font-family: "Courier New", monospace;
        font-weight: bold;
        color: var(--dark);
        line-height: 1.4;
    }

    .typing-cursor {
        display: inline-block;
        animation: blink 1s infinite;
    }

    /* --- Story --- */
    .story-container {
        max-width: 800px;
        margin: 0 auto;
    }

    .story-content p {
        margin-bottom: 1rem;
        font-size: 1.1rem;
        line-height: 1.8;
    }

    /* --- Team --- */
    .team-grid {
        display: grid;
        gap: 2rem;
        grid-template-columns: 1fr;
    }

    .team-avatar {
        height: 150px;
        border: var(--border-small);
        border-radius: 12px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-bottom: 1rem;
    }

    .avatar-icon {
        font-size: 4rem;
    }

    .team-role {
        font-family: var(--font-h1);
        color: var(--primary);
        font-size: 1.2rem;
        margin-bottom: 0.5rem;
        text-transform: uppercase;
    }

    .team-bio {
        font-size: 0.95rem;
        line-height: 1.5;
    }

    /* --- Stats --- */
    .stats-grid {
        display: grid;
        gap: 1rem;
        grid-template-columns: repeat(2, 1fr);
        margin-bottom: 2rem;
    }

    .stat-item {
        border: 2px solid #ddd;
        padding: 1rem;
        background: var(--light);
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }

    .stat-label {
        font-size: 0.8rem;
        text-transform: uppercase;
        font-weight: bold;
        opacity: 0.6;
    }

    .stat-value {
        font-family: var(--font-h1);
        font-size: 2rem;
        color: var(--dark);
        margin: 0.5rem 0;
    }

    .stat-change {
        font-size: 0.9rem;
        color: var(--secondary);
        font-weight: bold;
    }

    .loading-bar-container {
        display: flex;
        align-items: center;
        gap: 1rem;
        font-family: "Courier New", monospace;
        font-weight: bold;
    }

    .loading-bar {
        flex-grow: 1;
        height: 20px;
        border: var(--border-small);
        padding: 2px;
        background: #fff;
    }

    .loading-progress {
        height: 100%;
        width: 75%;
        background: repeating-linear-gradient(
                45deg,
                var(--primary),
                var(--primary) 10px,
                var(--primary) 10px,
                var(--primary) 20px
        );
    }

    /* --- FAQ --- */
    .faq-grid {
        display: grid;
        gap: 2rem;
    }

    .faq-question {
        font-family: var(--font-h1);
        color: var(--dark);
        margin-bottom: 0.5rem;
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

    /* --- Animations --- */
    @keyframes blink {
        0%, 100% { opacity: 1; }
        50% { opacity: 0; }
    }

    /* --- Responsive --- */
    @media (min-width: 768px) {
        .header-grid {
            grid-template-columns: 1fr 1fr;
        }

        .team-grid {
            grid-template-columns: repeat(3, 1fr);
        }

        .stats-grid {
            grid-template-columns: repeat(4, 1fr);
        }

        .faq-grid {
            grid-template-columns: 1fr 1fr;
        }
    }
</style>