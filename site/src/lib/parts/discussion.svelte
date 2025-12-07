<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import { base } from '$app/paths';
</script>

<section
	id="model"
	class="mt-30 mb-10 flex flex-col items-center justify-center gap-4 align-middle"
>
	<h1 class="text-center font-[HomeVideoBold-R90Dv] text-7xl text-[55px]">Discussion</h1>
	<p class="text-center font-[HomeVideo-ABLG6G]">What did we learn?</p>
	<Button href="#top" size="sm" variant="outline" class="font-[HomeVideo-ABLG6G]"
		>Back to top</Button
	>
</section>

<section class="mx-auto max-w-7xl font-[HomeVideo-ABLG6G]">
	<p class ="mx-auto max-w-4xl">In finality, our data shows that there exists significant correlations over online user sentiment with regards to vote turnouts in the Philippine midterm elections of 2025; having higher positive coefficients based on anger proportional to candidate votes, as based on our model. Neutral tonality was also found to correlate with higher polarity; favorability had interesting outputs despite correlating negative words to certain organizations still merited favorability. Unexpectedly, particular proponents in relation to candidates gave interesting insights over how words had contrasting polarities on varying partylists and candidates. 
	<br /><br/>
	Amongst the insights derived over the AI model, the researchers recognize the possibility over the limitations of the training process of the data, as the general pool of comments that were gathered were fixed onto a single platform limiting the diversity of inputs.
	<br /> <br/>
	For further enhancement over the exploration of these implications, we recommend integrating data across multiple social media applications to diversify the input, enhancing the features added to examine each comment or post.
</p>
</section>
