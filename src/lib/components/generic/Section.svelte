<script lang="ts">
	import Title from '$lib/components/generic/Title.svelte';

	export let title: string = "";
</script>

<section class="section">
	<Title level={2}>{title}</Title>
	<slot></slot>
</section>

<style>
    .section {
        margin: 4rem 0;
    }
</style>