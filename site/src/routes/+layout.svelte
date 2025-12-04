<script lang="ts">
	import { ModeWatcher } from 'mode-watcher';
	import '../app.css';
	import Button from '$lib/components/ui/button/button.svelte';
	let { children } = $props();
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu/index.js';
	import ThemeSwitcher from '$lib/components/ui/ThemeSwitcher.svelte';
</script>

<div
	class="sticky inset-0 top-0 left-0 z-20 mx-auto mb-0 hidden h-[70px] flex-col items-center justify-center gap-17 bg-background py-3 font-[HomeVideo-ABLG6G] md:flex md:flex-row"
>
	<Button href="#top">Home</Button>
	<DropdownMenu.Root>
		<DropdownMenu.Trigger><Button variant="outline">Our Datasets</Button></DropdownMenu.Trigger>
		<DropdownMenu.Content>
			<DropdownMenu.Group>
				<DropdownMenu.Item>
					<a
						href="https://docs.google.com/spreadsheets/d/1Ykn95ViscmLPN8v35FGxlBQ2KsmpfoZlW5jwcOtovqc/edit?usp=sharing"
						target="_blank"
						class="block px-4 py-2 text-sm focus:outline-hidden">Twitter Scrape Dataset Sheets</a
					></DropdownMenu.Item
				>
				<DropdownMenu.Item
					><a
						href="https://docs.google.com/spreadsheets/d/1pQp_xS_fyuA6Ip2ZN7SniKVbvQIyRTvXlAOP03bqUhk/edit?usp=sharing"
						target="_blank"
						class="block px-4 py-2 text-sm focus:outline-hidden">Senate Election Results Sheets</a
					></DropdownMenu.Item
				>
				<DropdownMenu.Item
					><a
						href="https://github.com/SSGonda/2025ElectionsInANutshell/tree/main/dataset/raw_data/election_results"
						target="_blank"
						class="block px-4 py-2 text-sm focus:outline-hidden">Partylist Election Results CSV</a
					></DropdownMenu.Item
				>
				<DropdownMenu.Item
					><a
						href="https://github.com/SSGonda/2025ElectionsInANutshell/tree/main/dataset/"
						target="_blank"
						class="block px-4 py-2 text-sm focus:outline-hidden">Dataset in Github Repository</a
					></DropdownMenu.Item
				>
			</DropdownMenu.Group>
		</DropdownMenu.Content>
	</DropdownMenu.Root>

	<Button href="#eda" size="lg" variant="ghost" class="rounded-xl px-5 text-base">
		<span class="text-nowrap">Our EDA.</span>
	</Button>

	<Button
		href="https://docs.google.com/document/d/1tlSUfIRb3os0wD-ZWfunGBFz90_re7mKh7p5uedNXUs/edit?usp=sharing"
		target="_blank"
		size="lg"
		variant="ghost"
		class="rounded-xl px-5"
	>
		Documentation
	</Button>

	<Button href="#model" size="lg" variant="ghost" class="rounded-xl px-5">Model</Button>

	<Button href="#about" size="lg" variant="ghost" class="rounded-xl px-5">About Us</Button>

	<ThemeSwitcher />
</div>

<ModeWatcher defaultMode={'dark'} defaultTheme={'dark'} />
{@render children()}
