<script lang="ts">
	import { base } from '$app/paths';
</script>

<div class="mb-20 flex flex-wrap">
	<div class="max-h-100 w-1/2 rounded-xl bg-[#1B181C] p-7">
		<img alt="nutshell plot" src="{base}/nutshell.png" />
	</div>

	<div class="w-1/2 px-10">
		<p class="text-2xl">Rage Begets Popularity</p>
		<p>
			In a nutshell, we found that senatorial candidates with extreme negative emotions or have
			negative opinions of have a substantial effect on a candidates votes, seeing the correlation
			of Anger, Contempt, Sadness, Polarity, and OpposedTo, it is noticed that they have moderate to
			strong positive correlations with their total amount of votes.
			<br />
			Interestingly, it is also seen that candidates who have Neutral tones and Unsure opinions also
			have a moderate to strong positive correlation, indicating that a 'middle-ground' size-fits-all
			candidate can be beneficial to attracting votes. <br />
			And with positive emotions and opinions, it is seen that there is little to no correlation with
			InFavor and Enjoyment Respectively. And with polarities, it is seen that there is a moderate negative
			correlation with votes, indicating that candidates with negative polarities tend to receive more
			votes, following the trend seen with negative emotions and opinions.
		</p>
	</div>
</div>

<div class="mb-25 flex flex-row bg-accent inset-shadow-2xs">
	<div class="min-w-1/2 content-center">
		<p class="border-r-2 border-r-accent-foreground text-center text-[40px]">
			No Partylists Correlations?
		</p>
	</div>
	<div class="p-6 text-right">
		It was found that the features extracted from the partylists' social media posts did not have
		any correlation with their votes, they were omitted for the correlation and modelling phase.
		<br />
	</div>
</div>
