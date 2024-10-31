<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<svelte:head>
	<title>HVCsano</title>
</svelte:head>

{@render children()}
