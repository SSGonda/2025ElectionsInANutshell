<script lang="ts">
	import type { PageProps } from './$types.js';
	let { data }: PageProps = $props();
	import About from '$lib/parts/about.svelte';
</script>

<About />
