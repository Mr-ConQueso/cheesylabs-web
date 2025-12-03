<script lang="ts">
	let { title = "", children, ...rest } = $props();
</script>

<div class="window" {...rest}>
	<div class="topbar">
		<div class="dots">
			<span class="dot red"></span>
			<span class="dot yellow"></span>
			<span class="dot green"></span>
		</div>
		<h3>{title}</h3>
	</div>

	<div class="content">
		{@render children?.()}
	</div>
</div>

<style>
    .window {
        background: var(--background);
        border: var(--border-big);
        border-radius: var(--radius);
        box-shadow: var(--shadow-big);
        overflow: hidden;
        margin: 2rem 0;
    }

    .topbar {
        background: var(--primary);
        padding: 0.2rem 1rem;
        border-bottom: var(--border-big);
        display: flex;
        align-items: center;
        gap: 1rem;
    }

    .dots {
        display: flex;
        gap: 0.4rem;
    }

    .dot {
        width: 14px;
        height: 14px;
        border-radius: 50%;
        border: var(--border-small);
				box-shadow: var(--shadow-small);
    }

    .red { background: var(--dark); }
    .yellow { background: var(--light); }
    .green { background: var(--light); }

    .content {
        padding: 1.5rem 2rem;
        font-family: var(--font-body);
    }
</style>