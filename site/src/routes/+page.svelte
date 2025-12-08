<script lang="ts">
	import Eda from '$lib/parts/eda.svelte';
	import Hero from '$lib/parts/hero.svelte';
	import About from '$lib/parts/about.svelte';
	import Background from '$lib/parts/background.svelte';
	import Model from '$lib/parts/model.svelte';
	import Discussion from '$lib/parts/discussion.svelte';
	import Conclusion from '$lib/parts/conclusion.svelte';
	import Nutshell from '$lib/parts/nutshell.svelte';
</script>

<main>
	<section id="top" class="mx-auto mt-10 max-w-5xl font-[HomeVideo-ABLG6G]">
		<Hero />
		<Nutshell />
		<!-- The Wobblers -->
		<Background />
	</section>

	<Eda />
	<Model />
	<Discussion />
	<Conclusion />
	<About />
</main>
