<script lang="ts">
	import Eda from '$lib/parts/eda.svelte';
	import Hero from '$lib/parts/hero.svelte';
	import About from '$lib/parts/about.svelte';
	import Background from '$lib/parts/background.svelte';
	import { base } from '$app/paths';
</script>

<main>
	<section id="top" class="mx-auto mt-10 max-w-5xl font-[HomeVideo-ABLG6G]">
		<Hero />

		<!-- Nutshell Plot -->
		<div class="flex flex-wrap">
			<div class="w-1/2">
				<img class="" alt="tmp" src="{base}/image1.png" />
			</div>

			<div class="w-1/2 px-10">
				<p class="text-2xl">What we Found...</p>
				<p>
					An overview on the effects and relationships of Social Media Exposure to the 2025
					Philippine Midterm Election.An overview on the effects and relationships of Social Media
					Exposure to the 2025 Philippine Midterm Election. An overview on the effects and
					relationships of Social Media Exposure to the 2025 Philippine Midterm Election. An
					overview on the effects and relationships of Social Media Exposure to the 2025 Philippine
					Midterm Election.An overview on the effects and relationships of Social Media Exposure to
					the 2025 Philippine Midterm Election.An overview on the effects and relationships of
					Social Media Exposure to the 2025 Philippine Midterm Election.An overview on the effects
					and relationships of Social Media Exposure to the 2025 Philippine Midterm Election.
				</p>
			</div>
		</div>

		<!-- The Wobblers -->
		<Background />
	</section>

	<Eda />
	<About />
</main>
