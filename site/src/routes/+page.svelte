<script lang="ts">
	import Eda from '$lib/parts/eda.svelte';
	import Hero from '$lib/parts/hero.svelte';
	import About from '$lib/parts/about.svelte';
	import Background from '$lib/parts/background.svelte';
	import Model from '$lib/parts/model.svelte';
	import Discussion from '$lib/parts/discussion.svelte';
	import Conclusion from '$lib/parts/conclusion.svelte';
	import { base } from '$app/paths';
</script>

<main>
	<section id="top" class="mx-auto mt-10 max-w-5xl font-[HomeVideo-ABLG6G]">
		<Hero />

		<!-- Nutshell Plot -->
		<div class="flex flex-wrap">
			<div class="max-h-100 w-1/2 rounded-xl bg-[#1B181C] p-7">
				<img alt="nutshell plot" src="{base}/nutshell.png" />
			</div>

			<div class="w-1/2 px-10">
				<p class="text-2xl">What we Found...</p>
				<p>
					In a nutshell, we found that senatorial candidates with extreme negative emotions or have
					negative opinions of have a substantial effect on a candidates votes, seeing the
					correlation of Anger, Contempt, Sadness, Polarity, and OpposedTo, it is noticed that they
					have moderate to strong positive correlations with their total amount of votes.
					<br />
					Interestingly, it is also seen that candidates who have Neutral tones and Unsure opinions also
					have a moderate to strong positive correlation, indicating that a 'middle-ground' size-fits-all
					candidate can be beneficial to attracting votes. <br />
					And with positive emotions and opinions, it is seen that there is little to no correlation
					with InFavor and Enjoyment Respectively. And with polarities, it is seen that there is a moderate
					negative correlation with votes, indicating that candidates with negative polarities tend to
					receive more votes, following the trend seen with negative emotions and opinions.
					<br />
					A nutshell plot was not made for partylists, as it was found that all partylist categories have no
					correlation to a partylist's votes, this may be from having a small amount of data for partylists from
					the initial scraping done.
					<br /><br />
					As a whole, it is seen that having a good social media presence, especially when negative, or having a
					neutral 'middle-ground' stance tend to give more votes for a senatorial candidate.
				</p>
			</div>
		</div>

		<!-- The Wobblers -->
		<Background />
	</section>

	<Eda />
	<Model />
	<Discussion />
	<Conclusion />
	<About />
</main>
