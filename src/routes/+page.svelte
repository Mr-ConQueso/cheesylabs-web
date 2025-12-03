<script lang="ts">
	import Window from "$lib/components/Window.svelte";
	import Section from "$lib/components/Section.svelte";
	import Button from "$lib/components/Button.svelte";
	import Title from "$lib/components/Title.svelte";
</script>

<!-- ============================= -->
<!--          HERO / CTA           -->
<!-- ============================= -->
<Window title="Welcome to Cheesy Labs">
	<Title level={1}>Delightfully Silly. Seriously Creative.</Title>

	<p>
		At Cheesy Labs, we craft games, apps, tools, and experiments with style,
		charm, and a pinch of retro-cartoon magic.
	</p>

	<Button label="Explore Our Work" href="#projects" />
</Window>

<!-- ============================= -->
<!--         PROJECTS LIST         -->
<!-- ============================= -->
<Section title="Projects">
	<Window title="Our Latest Experiments">
		<h3>🧀 Project Alpha</h3>
		<p>Whimsical prototype exploring physics and cheese-based propulsion.</p>

		<h3>🔬 ConQueso Engine</h3>
		<p>Creative toolkit mixing animation, particles, and gooey cartoon FX.</p>

		<h3>🎨 Nölme Learning App</h3>
		<p>Tolkien-language learning experience featuring custom STT/TTS tech.</p>
	</Window>
</Section>

<!-- ============================= -->
<!--            FAQ                -->
<!-- ============================= -->
<Section title="FAQ">
	<Window title="Frequently Asked Questions">
		<h3>What exactly does Cheesy Labs do?</h3>
		<p>
			Cheesy Labs blends experimentation, animation, and development into
			delightful digital creations.
		</p>

		<h3>Is everything made by one person?</h3>
		<p>
			Cheesy Labs is the mad science extension of Mr. ConQueso — but
			collaborations bubble in the lab too!
		</p>

		<h3>Can I work with you?</h3>
		<p>
			Absolutely! Send a message and the lab door swings right open.
		</p>
	</Window>
</Section>

<!-- ============================= -->
<!--           FOOTER              -->
<!-- ============================= -->
<footer style="
  margin: 4rem 0;
  text-align: center;
  color: var(--light);
  font-family: var(--font-body);
">
	CHEESY LABS — © 2025
</footer>