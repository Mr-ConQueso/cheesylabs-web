<script lang="ts">
	export let title: string = "";
</script>

<div class="window">
	<div class="topbar">
		<div class="dots">
			<span class="dot red"></span>
			<span class="dot yellow"></span>
			<span class="dot green"></span>
		</div>
		<h3>{title}</h3>
	</div>

	<div class="content">
		<slot></slot>
	</div>
</div>

<style>
    .window {
        background: var(--background);
        border: var(--border);
        border-radius: var(--radius);
        box-shadow: var(--shadow-big);
        overflow: hidden;
        margin: 2rem 0;
    }

    .topbar {
        background: var(--primary);
        padding: 0.75rem 1rem;
        border-bottom: var(--border);
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
        border: var(--border);
    }

    .red { background: #ff5f57; }
    .yellow { background: #ffbd2e; }
    .green { background: #27c93f; }

    .content {
        padding: 1.5rem 2rem;
        font-family: var(--font-body);
    }
</style>