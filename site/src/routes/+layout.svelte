<script lang="ts">
	import { ModeWatcher } from 'mode-watcher';
	import '../app.css';
	import ThemeSwitcher from '$lib/components/ui/ThemeSwitcher.svelte';

	let { children } = $props();
</script>

<ModeWatcher defaultMode={'dark'} defaultTheme={'dark'}/>
{@render children()}
<!-- <ThemeSwitcher /> -->
