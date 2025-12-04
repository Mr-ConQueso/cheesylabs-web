<script lang="ts">
	import favicon from '/icons/favicon.svg';
	import '../app.css';
	import Navbar from '$lib/components/navigation/Navbar.svelte';
	import Footer from '$lib/components/navigation/Footer.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Cheesy Labs</title>
</svelte:head>

<Navbar />

{@render children()}

<!--<Banner />-->

<Footer />