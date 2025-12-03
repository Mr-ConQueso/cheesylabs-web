<script lang="ts">
	export let level: 1 | 2 | 3 | 4 = 1;
</script>

<svelte:element this={"h" + level} class="title">
	<slot></slot>
</svelte:element>

<style>
    .title {
        font-family: var(--font-h1);
        color: var(--dark);
        text-shadow: var(--shadow-small);
        margin: 1.5rem 0 1rem 0;
    }

    .title h1 {
        font-family: var(--font-h1);
        font-size: 3rem;
    }
</style>