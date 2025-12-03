<script lang="ts">
	export let label: string;
	export let href: string | null = null;
</script>

<a class="btn" href={href ?? "#"}>
	{label}
	<span class="arrow">➜</span>
</a>

<style>
    .btn {
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.8rem 1.4rem;
        background: var(--light);
        border: var(--border);
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