<script lang="ts">
	import '$lib/scss/app.scss';
</script>

<svelte:head>
	<title>Temperature Converter</title>
</svelte:head>

<main>
	<slot />
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		position: relative;
		height: 100vh;
	}
</style>
