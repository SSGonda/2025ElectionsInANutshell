<script lang="ts">
	import type { PageProps } from './$types.js';
	import Button from '$lib/components/ui/button/button.svelte';
	import { base } from '$app/paths';
    import Particles from '$lib/components/ui/Particles.svelte';

	let { data }: PageProps = $props();
</script>

<section class="mt-30 mb-30 flex flex-col items-center justify-center gap-4 align-middle">
	<h1 class="text-center text-7xl font-[HomeVideoBold-R90Dv] text-[55px]">Our Plots.</h1>
	<p class="font-[HomeVideo-ABLG6G] text-center">An overview on the effects and relationships <br>
		of Social Media Exposure to the 2025 <br>
		Philippine Midterm Election.</p>
	<Button href="{base}/" size="sm" variant="outline" class="font-[HomeVideo-ABLG6G]">Go Back Home</Button>
</section>

<section class="flex flex-col items-center justify-center gap-2 align-middle font-[HomeVideo-ABLG6G]">
	<div class="flex max-w-4xl flex-col gap-3">
		<h1 class="text-3xl">
			EDA and Sentiment Analysis Notebooks [<a
				class="text-blue-950"
				href="https://deepnote.com/workspace/thing-a23c5647-fae1-450c-a5f9-b8d323581852/project/Stephens-Untitled-project-379262c2-f7d6-45ba-811e-59f3f72f9143/notebook/EDA2025MidtermHalalanSentimentAnalysisllama4maverick-c09ebae9fc814360b6c7f79efc6ae3d3"
				>link</a
			>]
		</h1>

		<p>
			Deepnote was opted to be used as this offered easier collaboration options and provided a
			‘link’ between 2 notebooks to access the same set of data at any time.
		</p>

		<h1 class="text-3xl">Context of the Sentiments Dataset</h1>
		<p>
			Prior to performing the EDA, each tweet was ran through an LLM
			(meta-llama/llama-4-maverick-17b-128e-instruct) to perform sentiment analysis in which the
			following attributes were determined per tweet,
		</p>
		<ul class="list-inside list-disc space-y-4">
			<li>The mentioned candidate or partylist</li>
			<li>
				The polarity of the tweet, with -1 being negative and 1 being positive, floating point
				values accepted, both exclusive
			</li>
			<li>
				The tone of the tweet which may be
				<ul class="mt-2 list-inside list-decimal space-y-1 ps-7">
					<li>Anger</li>
					<li>Contempt</li>
					<li>Disgust</li>
					<li>Enjoyment</li>
					<li>Fear</li>
					<li>Sadness</li>
					<li>Surprise</li>
					<li>Neutral</li>
				</ul>
			</li>
			<li>
				The ‘Perceived Judgement’ of a user towards their mentioned candidate, which may be either
				<ul class="mt-2 list-inside list-decimal space-y-1 ps-7">
					<li>In favor</li>
					<li>Unsure</li>
					<li>Opposed to</li>
				</ul>
			</li>
		</ul>
		<p>
			In the case that multiple candidates were mentioned in a tweet, a list will be returned
			containing the corresponding tone, polarity, and judgement per candidate mentioned in that
			tweet. The particular model, meta-llama/llama-4-maverick-17b-128e-instruct, was used for its
			balance between speed, price, and accuracy based on its benchmarks on analysis (Artificial
			Index, 2025).
		</p>

		<h1 class="text-3xl">Hypotheses under Correlation and Normality Tests</h1>

		<h2>Normality Test</h2>

		<pre class="self-center-safe">
Senators → Chi-square=9.600, p=0.143, dof=6
votes_cat     Low  Mid-Low  Mid-High  High
polarity_cat                              
Negative        3        1         0     1
Neutral         0        1         0     1
Positive        0        1         3     1 

Partylists → Chi-square=3.281, p=0.773, dof=6
votes_cat     Low  Mid-Low  Mid-High  High
polarity_cat                              
Negative        0        1         1     1
Neutral         1        0         0     1
Positive        5        4         4     3 

All → Chi-square=11.330, p=0.079, dof=6
votes_cat     Low  Mid-Low  Mid-High  High
polarity_cat                              
Negative        1        1         5     1
Neutral         1        0         1     2
Positive        7        7         2     5 
		</pre>

		<p>With p &gt; 0.05 for all cases, the null hypothesis is accepted, that is, the data does not follow a normal distribution</p>
		<p>Although Pearson Correlation and Spearman Correlation do not assume normality, with this, they may still be used to test for correlation.</p>

		<h2>Correlation Tests</h2>

		<figure class="flex flex-col justify-center">
			<img class="self-center-safe rounded-2xl" src="{base}/image3.png" alt="Pearson Correlation Plot" />
			<figcaption class="text-center font-light">
				Figure 1. Pearson Correlation of Total Votes in Relation to the Average Polarity of Each
				Senatorial Candidate
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image1.png"
				alt="Spearman's Rank Correlation Plot"
			/>
			<figcaption class="text-center font-light">
				Figure 2. Spearman's Rank Correlation of Total Votes with respect to the Average Polarity of
				Each Senatorial Candidate
			</figcaption>
		</figure>

		<section class="space-y-4">
			<div>
				<h2>Null</h2>
				<p>
					Social media sentiments have no significant level of influence on the likelihood of being
					elected a Candidate during the 2025 Philippine National and Local Elections.
				</p>
			</div>

			<div>
				<h2>Alternative</h2>
				<p>
					Social media sentiments have a significant level of influence on the likelihood of being
					elected a Candidate during the 2025 Philippine National and Local Elections.
				</p>
			</div>

			<div>
				<h2>Conclusion</h2>
				<p>Pearson correlation coefficient (polarity vs votes): -0.2784966690117171</p>
				<p>Spearman correlation coefficient (polarity vs votes): -0.3678864219767173</p>
				<p>
					Which is interpreted as a negative moderate correlation, therefore, we reject the null
					hypothesis. (Research Gate, 2018)
				</p>
			</div>
		</section>

		<h1 class="text-2xl">Research Questions</h1>

		<h2 class="text-xl">
			How did emotions impact the candidates to be chosen for the elections?
		</h2>

		<figure class="flex flex-col justify-center">
			<img class="self-center-safe rounded-2xl" src="{base}/image6.png" alt="Tone Counts Plot" />
			<figcaption class="text-center font-light">
				Figure 3. Tone counts across the entire dataset containing the sentiments of each tweet.
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img class="self-center-safe rounded-2xl" src="{base}/image13.png" alt="Polarities Counts Plot" />
			<figcaption class="text-center font-light">
				Figure 4. Counts of Polarities across the entire dataset containing the sentiments of each
				tweet, colored by the tweet's associated tone.
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image9.png"
				alt="Heatmap of Tone Instances for Winning Candidates"
			/>
			<figcaption class="text-center font-light">
				Figure 5. Heatmap of the amount of instances of tone in relation to the subset of winning
				senatorial candidates across all tweets.
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image2.png"
				alt="Heatmap of Tone Instances for All Candidates"
			/>
			<figcaption class="text-center font-light">
				Figure 6. Heatmap of the amount of instances of tone in relation to the partylists mentioned
				across all tweets.
			</figcaption>
		</figure>

		<h2 class="text-xl">
			What are the critical proponents that shape the decisions of Filipino voters over support for
			a candidate?
		</h2>

		<figure class="flex flex-col justify-center">
			<img class="self-center-safe rounded-2xl" src="{base}/image5.png" alt="Word Cloud Plot" />
			<figcaption class="text-center font-light">
				Figure 7. A word cloud of the most mentioned words or phrases across the entire Tweets
				Dataset.
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image4.png"
				alt="Heatmap of Associated Words vs Average Polarity"
			/>
			<figcaption class="text-center font-light">
				Figure 8. A heatmap of the associated word of a tweet in relation to the mentioned
				senatorial candidate, with the heat being the average polarity of a user in the tweet.
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image8.png"
				alt="Heatmap of Associated Words vs Polarity"
			/>
			<figcaption class="text-center font-light">
				Figure 9. A heatmap of the associated word in a tweet in relation to the mentioned
				partylist, with the heat being the polarity of the said tweet.
			</figcaption>
		</figure>

		<h2 class="text-xl ">
			How much did online social media sentiments influence actions over the elections?
		</h2>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image11.png"
				alt="Heatmap of Perceived Judgement and Senatorial Candidates"
			/>
			<figcaption class="text-center font-light">
				Figure 10. A heatmap of the perceived judgement of a user towards their mentioned senatorial
				candidate in a tweet, with the heat being the amount of instances of that judgement per
				candidate.
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image7.png"
				alt="Heatmap of Perceived Judgement and Partylists"
			/>
			<figcaption class="text-center font-light">
				Figure 11. A heatmap of the perceived judgement of a user towards their mentioned partylist
				in a tweet, with the heat being the amount of instances of that judgement per candidate.
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image12.png"
				alt="Pie Chart of Senatorial Candidates Mentions"
			/>
			<figcaption class="text-center font-light">
				Figure 12. A pie chart showing the percentage of senatorial candidates mentioned in relation
				to the dataset (tweets containing mentioning a candidate), ordered by amount, candidates
				with less than 3 mentions or past the top 10 are marked as others.
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image10.png"
				alt="Pie Chart of Partylist Mentions"
			/>
			<figcaption class="text-center font-light">
				Figure 13. A pie chart showing the percentage of partylists mentioned in relation to the
				dataset (tweets containing a mention of a partylist), ordered by amount. With partylists
				past the Top 10 being marked as 'others'.
			</figcaption>
		</figure>

		<p>
			The correlation tests done in the hypothesis testing earlier may also be used for this
			research question.
		</p>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image3.png"
				alt="Pearson Correlation of Total Votes vs Average Polarity"
			/>
			<figcaption class="text-center font-light">
				Figure 14. Pearson Correlation of Total Votes in Relation to the Average Polarity of Each
				Senatorial Candidate
			</figcaption>
		</figure>

		<figure class="flex flex-col justify-center">
			<img
				class="self-center-safe rounded-2xl"
				src="{base}/image1.png"
				alt="Spearman's Rank Correlation of Total Votes vs Average Polarity"
			/>
			<figcaption class="text-center font-light">
				Figure 15. Spearman's Rank Correlation of Total Votes with respect to the Average Polarity
				of Each Senatorial Candidate
			</figcaption>
		</figure>

		<h2 class="text-xl">
			Are we able to predict the influence of social media on nationwide elections?
		</h2>
		<p>To be answered in the modelling stage</p>

		<h2 class="mb-4 text-2xl ">References</h2>
		<ul class="space-y-2">
			<li>Artificial Analysis. (2025). Artificial analysis. https://artificialanalysis.ai/</li>
			<li>
				Research Gate. (2018). Interpretation of the Pearson's and Spearman's correlation
				coefficients. Research Gate.
				https://www.researchgate.net/figure/nterpretation-of-the-Pearsons-and-Spearmans-correlation-coefficients_tbl1_326885374
			</li>
		</ul>
	</div>

	<Particles className="absolute inset-0 -z-10" refresh={true} />
</section>
