<script>
	import favicon from '$lib/assets/favicon.svg';
	import { base } from '$app/paths';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<nav class="nav">
	<a href={base + '/'}>App</a>
	<a href={base + '/projekt'}>Projektbeschreibung</a>
	<a href="https://github.com/ken-lampugnani/agenda-app-devops" target="_blank" rel="noreferrer">Repository</a>
</nav>

<main class="content">
	{@render children()}
</main>

<style>
	.nav {
		display: flex;
		gap: 12px;
		padding: 12px 0;
		margin-bottom: 16px;
		border-bottom: 1px solid #ddd;
	}

	.content {
		padding-top: 8px;
	}
</style>