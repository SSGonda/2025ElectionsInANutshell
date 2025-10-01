<script lang="ts">
    import type { PageProps } from './$types.js';
    import Button from '$lib/components/ui/button/button.svelte';
	import Particles from '$lib/components/ui/Particles.svelte';
    import { base } from '$app/paths';

    let { data }: PageProps = $props();
</script>

<section class="mt-10 mb-30 flex flex-col gap-6 items-center align-middle justify-center">
    <h1 class="text-7xl font-bold text-center ">Datasets</h1>
    <Button
        href="{base}/"
        size="sm"
        variant="secondary"
    >
        Go Back Home
    </Button>
</section>

<section class="flex flex-col gap-2 items-center align-middle justify-center">
    <Button
        href="https://docs.google.com/spreadsheets/d/1Ykn95ViscmLPN8v35FGxlBQ2KsmpfoZlW5jwcOtovqc/edit?usp=sharing"
        target="_blank"
        size="lg"
        class="rounded-xl px-5"
    >
        Twitter Scrape Dataset Sheets
    </Button>
    <Button
        href="https://docs.google.com/spreadsheets/d/1pQp_xS_fyuA6Ip2ZN7SniKVbvQIyRTvXlAOP03bqUhk/edit?usp=sharing"
        target="_blank"
        size="lg"
        class="rounded-xl px-5"
    >
        Senate Election Results Sheets
    </Button>
    <Button
        href="https://github.com/SSGonda/2025ElectionsInANutshell/tree/main/dataset/raw_data/election_results"
        target="_blank"
        size="lg"
        class="rounded-xl px-5"
    >
        Partylist Election Results CSV (File too big for Google Sheets)
    </Button>
    <Button
        href="https://github.com/SSGonda/2025ElectionsInANutshell/tree/main/dataset/"
        target="_blank"
        size="lg"
        class="rounded-xl px-5"
    >
        Dataset in Github Repository
    </Button>
    <Particles className="absolute inset-0 -z-10" refresh={true} />
</section>
