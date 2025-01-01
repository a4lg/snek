<script lang="ts">
	import favicon from '$lib/images/favicon.png';
	import { page } from '$app/state';
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="app">
	<nav>
		<!-- svelte-ignore a11y_invalid_attribute it's valid in this context -->
		<a href="" aria-current={page.route.id === '/'}>home</a>
		<a href="#/about" aria-current={page.route.id === '/about'}>about</a>

		{#if page.url.protocol !== 'file:'}
			<!-- svelte-ignore a11y_invalid_attribute -->
			<a href="" download="snek.html">download this game</a>
		{/if}
	</nav>

	<main>
		{@render children()}
	</main>
</div>

<style>
	.app {
		display: grid;
		grid-template-rows: 4em 1fr 4em;
		min-height: 100vh;
		justify-content: center;
	}

	nav {
		padding: 1em;
		text-align: center;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
		justify-content: center;
	}
</style>
