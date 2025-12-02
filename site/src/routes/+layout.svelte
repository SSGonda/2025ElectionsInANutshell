<script lang="ts">
	import { ModeWatcher } from 'mode-watcher';
	import '../app.css';
	import { base } from '$app/paths';
	import Button from '$lib/components/ui/button/button.svelte';
	let { children } = $props();
	import '@tailwindplus/elements';
</script>

<div class="mt-7 flex flex-col items-center justify-center gap-50 md:flex-row">

	<el-dropdown class="inline-block relative z-50">
		<button class="inline-flex w-full justify-center gap-x-1.5 rounded-md bg-white/10 px-3 py-2 text-sm text-white inset-ring-1 inset-ring-white/5 hover:bg-white/20">
		Our Datasets.
		<svg viewBox="0 0 20 20" fill="currentColor" data-slot="icon" class="-mr-1 size-5 text-gray-400">
			<path d="M5.22 8.22a.75.75 0 0 1 1.06 0L10 11.94l3.72-3.72a.75.75 0 1 1 1.06 1.06l-4.25 4.25a.75.75 0 0 1-1.06 0L5.22 9.28a.75.75 0 0 1 0-1.06Z" clip-rule="evenodd" fill-rule="evenodd" />
		</svg>
		</button>

		<el-menu anchor="bottom end" popover class="w-56 origin-top-right rounded-md bg-gray-800 outline-1 -outline-offset-1 outline-white/10 transition transition-discrete [--anchor-gap:--spacing(2)] data-closed:scale-95 data-closed:transform data-closed:opacity-0 data-enter:duration-100 data-enter:ease-out data-leave:duration-75 data-leave:ease-in">
		<div class="py-1">
			<a href="https://docs.google.com/spreadsheets/d/1Ykn95ViscmLPN8v35FGxlBQ2KsmpfoZlW5jwcOtovqc/edit?usp=sharing" class="block px-4 py-2 text-sm text-gray-300 focus:bg-white/5 focus:text-white focus:outline-hidden">Twitter Scrape Dataset Sheets</a>
			<a href="https://docs.google.com/spreadsheets/d/1pQp_xS_fyuA6Ip2ZN7SniKVbvQIyRTvXlAOP03bqUhk/edit?usp=sharing" class="block px-4 py-2 text-sm text-gray-300 focus:bg-white/5 focus:text-white focus:outline-hidden">Senate Election Results Sheets</a>
			<a href="https://github.com/SSGonda/2025ElectionsInANutshell/tree/main/dataset/raw_data/election_results" class="block px-4 py-2 text-sm text-gray-300 focus:bg-white/5 focus:text-white focus:outline-hidden">Partylist Election Results CSV</a>
			<a href="https://github.com/SSGonda/2025ElectionsInANutshell/tree/main/dataset/" class="block px-4 py-2 text-sm text-gray-300 focus:bg-white/5 focus:text-white focus:outline-hidden">Dataset in Github Repository</a>
		</div>
		</el-menu>
	</el-dropdown>

	<Button
		href="{base}/plots"
		size="lg"
		variant="ghost"
		class="rounded-xl px-5 text-base">
		<span class="text-nowrap">Our EDA.</span>
	</Button>

	<Button
		href="https://docs.google.com/document/d/1tlSUfIRb3os0wD-ZWfunGBFz90_re7mKh7p5uedNXUs/edit?usp=sharing"
		target="_blank"
		size="lg"
		variant="ghost"
		class="rounded-xl px-5">
		Documentation
	</Button>

	<Button href="{base}/aboutus" size="lg" variant="ghost" class="rounded-xl px-5">
		About Us
	</Button>
</div>

<ModeWatcher defaultMode={'dark'} defaultTheme={'dark'} />
{@render children()}
<!-- <ThemeSwitcher /> -->

<style>
	.mt-7{
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 70px;
		font-family: 'HomeVideo-ABLG6G';
	}
</style>
