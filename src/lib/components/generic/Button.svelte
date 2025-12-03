<script lang="ts">
	let { href = null, children, ...rest }: {
		href?: string | null;
		children?: any;
	} = $props();
</script>

<a class="btn" href={href ?? "#"} {...rest}>
	{@render children?.()}
	<span class="arrow">➜</span>
</a>

<style>
    .btn {
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.8rem 1.4rem;
        background: var(--light);
        border: var(--border-big);
        border-radius: var(--radius);
        font-family: var(--font-h);
        color: var(--dark);
        text-decoration: none;
        box-shadow: var(--shadow-small);
        transition: transform 0.1s;
    }

    .btn:hover {
        transform: translate(-2px, -2px);
    }
</style>