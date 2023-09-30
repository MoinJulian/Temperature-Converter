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
		max-width: 40rem;
		margin-inline: 0 auto;
		padding-inline: 1rem;
	}
</style>
