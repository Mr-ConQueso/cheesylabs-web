<script lang="ts">
	let { level = 1, children, ...rest }: {
		level?: 1 | 2 | 3 | 4;
		children?: any;
	} = $props();
</script>

<svelte:element this={"h" + level} class="title" {...rest}>
	{@render children?.()}
</svelte:element>

<style>
    .title {
        font-family: var(--font-h1);
        color: var(--primary);
        text-shadow: var(--shadow-medium);
        margin: 1.5rem 0 1rem 0;
    }

    .title h1 {
				color: var(--primary);
        font-family: var(--font-h1);
        font-size: 3rem;
    }
</style>