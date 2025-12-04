<script>
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';
	onMount(async () => {
		if (browser) {
			const Plotly = await import('plotly.js-dist-min');
			// add here
		}
	});
</script>
