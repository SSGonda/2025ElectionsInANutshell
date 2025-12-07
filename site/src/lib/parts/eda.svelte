<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import { base } from '$app/paths';
	import CandidatesPie from '$lib/plots/candidates_pie.svelte';
	import PartylistsPie from '$lib/plots/partylists_pie.svelte';
	import ToneBar from '$lib/plots/tone_bar.svelte';
	import PolaritiesBar from '$lib/plots/polarities_bar.svelte';
</script>

<section id="eda" class="mt-40 mb-10 flex flex-col items-center justify-center gap-4 align-middle">
	<h1 class="text-center font-[HomeVideoBold-R90Dv] text-7xl text-[55px]">
		Lets look at the Data.
	</h1>
	<p class="text-center font-[HomeVideo-ABLG6G]">
		An overview on the effects and relationships <br />
		of Social Media Exposure to the 2025 <br />
		Philippine Midterm Election.
	</p>
	<Button href="#top" size="sm" variant="outline" class="font-[HomeVideo-ABLG6G]"
		>Back to top</Button
	>
</section>

<section class="mx-auto max-w-7xl font-[HomeVideo-ABLG6G]">
	<div class="mx-20 mb-30 flex flex-row text-right">
		<div class="flex-1 content-center border-r-2 border-r-white">
			<div class="m-2 flex">
				<p class="mr-3 rounded-lg bg-[#d9d9d9] px-4 py-0.5 text-center text-lg text-[#190a2f]">
					1.
				</p>
				<p class="text-lg">the mentioned candidate or partylist</p>
			</div>

			<div class="m-2 flex">
				<p class="mr-3 rounded-lg bg-[#d9d9d9] px-4 py-0.5 text-center text-lg text-[#190a2f]">
					2.
				</p>
				<p class="text-lg">the polarity of the tweet</p>
			</div>

			<div class="m-2 flex">
				<p class="mr-3 rounded-lg bg-[#d9d9d9] px-4 py-0.5 text-center text-lg text-[#190a2f]">
					3.
				</p>
				<p class="text-lg">the tone of the tweet</p>
			</div>

			<div class="m-2 flex">
				<p class="mr-3 rounded-lg bg-[#d9d9d9] px-4 py-0.5 text-center text-lg text-[#190a2f]">
					4.
				</p>
				<p class="text-lg">the 'perceived judgement' of a user</p>
			</div>
		</div>

		<div class="flex w-1/2 flex-col">
			<p class="text-4xl">
				Context of the <br />
				Sentiments Dataset
			</p>
			<p class="mt-5 mb-5 ml-10">
				Prior to performing the EDA, each tweet was ran through an LLM
				(meta-llama/llama-4-maverick-17b-128e-instruct) to perform sentiment analysis in which the
				following attributes were determined per tweet.
				<br /><br />
				In the case that multiple candidates were mentioned in a tweet, a list will be returned containing
				the corresponding tone, polarity, and judgement per candidate mentioned in that tweet. The particular
				model, meta-llama/llama-4-maverick-17b-128e-instruct, was used for its balance between speed,
				price, and accuracy based on its benchmarks on analysis (Artificial Index, 2025).
			</p>
		</div>
	</div>

	<div class="mb-25 flex flex-row bg-accent inset-shadow-2xs">
		<div class="min-w-1/2 content-center">
			<p class="border-r-2 border-r-accent-foreground text-center text-[40px]">
				EDA and Sentiment <br /> analysis notebooks
			</p>
		</div>
		<div class="p-6 text-right">
			We used Deepnote to perform our EDA and Sentiment Analysis, for sharing, we copied our
			notebooks to Google Colab, as Deepnote did not have a 'anyone can view' option.
			<br />
			<Button
				href="https://colab.research.google.com/drive/1WO7hBTd_YooUGeEUDEmEZZdoMO5__Ngt?usp=sharing"
				size="sm"
				variant="default"
				target="_blank"
				class="align-left m-5">EDA notebook</Button
			>
		</div>
	</div>

	<div class="mb-25 flex flex-row p-5">
		<div class="w-1/2 border-r-2 border-r-accent-foreground p-10">
			<h1 class="text-[40px]">Hypotheses under Correlation and Normality Tests</h1>

			<div>
				<p>
					With p &gt; 0.05 for all cases, the null hypothesis is accepted, that is, the data does
					not follow a normal distribution. Although Pearson Correlation and Spearman Correlation do
					not assume normality, with this, they may still be used to test for correlation.
				</p>
			</div>

			<div>
				<h2 class="underline"><br />Null</h2>
				<p>
					Social media sentiments have no significant level of influence on the likelihood of being
					elected a Candidate during the 2025 Philippine National and Local Elections.
				</p>
				<br />
			</div>

			<div>
				<h2 class="underline">Alternative</h2>
				<p>
					Social media sentiments have a significant level of influence on the likelihood of being
					elected a Candidate during the 2025 Philippine National and Local Elections.
				</p>
			</div>
		</div>

		<div class="w-1/2 content-center">
			<h2 class="m-2 mb-3 underline">Normality Test</h2>
			<div class=" m-2 content-center rounded-lg bg-[#d9d9d93f] p-2">
				<pre class="whitespace-pre-wrap">
			Senators → Chi-square=9.600, p=0.143, dof=6
			votes_cat     Low  Mid-Low  Mid-High  High
			polarity_cat                              
			Negative        3        1         0     1
			Neutral         0        1         0     1
			Positive        0        1         3     1 
		</pre>
			</div>

			<div class=" m-2 content-center rounded-lg bg-[#b02465] p-2">
				<pre class="whitespace-pre-wrap text-white">
			Partylists → Chi-square=3.281, p=0.773, dof=6
			votes_cat     Low  Mid-Low  Mid-High  High
			polarity_cat                              
			Negative        0        1         1     1
			Neutral         1        0         0     1
			Positive        5        4         4     3 
		</pre>
			</div>

			<div class=" m-2 content-center rounded-lg bg-[#392cad] p-2">
				<pre class="whitespace-pre-wrap text-white">
			All → Chi-square=11.330, p=0.079, dof=6
			votes_cat     Low  Mid-Low  Mid-High  High
			polarity_cat                              
			Negative        1        1         5     1
			Neutral         1        0         1     2
			Positive        7        7         2     5 
		</pre>
			</div>
		</div>
	</div>

	<div class="mb-20 flex flex-row rounded-lg bg-accent">
		<div>
			<h2 class="text-md p-6 underline">Correlation Tests</h2>
			<div class="flex flex-row p-2">
				<figure class="m-2">
					<img
						class="mb-2 self-center-safe"
						src="{base}/image1.png"
						alt="Spearman's Rank Correlation Plot"
					/>
					<figcaption class="text-xs">
						Figure 2. Spearman's Rank Correlation of Total Votes with respect to the Average
						Polarity of Each Senatorial Candidate
					</figcaption>
				</figure>

				<figure class="m-2">
					<img
						class="mb-2 self-center-safe"
						src="{base}/image3.png"
						alt="Pearson Correlation Plot"
					/>
					<figcaption class="text-xs">
						Figure 1. Pearson Correlation of Total Votes in Relation to the Average Polarity of Each
						Senatorial Candidate
					</figcaption>
				</figure>
			</div>
		</div>

		<div class="w-1/2 content-center bg-primary p-3 text-accent">
			<h2 class="text-center text-3xl underline">Conclusion</h2>
			<div class="flex flex-col p-3 text-center">
				<p>Pearson correlation coefficient (polarity vs votes): -0.2784966690117171 <br /><br /></p>
				<p>
					Spearman correlation coefficient (polarity vs votes): -0.3678864219767173 <br /><br />
				</p>
				<p>
					Which is interpreted as a negative moderate correlation, therefore, we reject the null
					hypothesis. (Research Gate, 2018)
				</p>
			</div>
		</div>
	</div>

	<div class="content-center">
		<h1 class="mb-[45px] text-center text-4xl underline">Our Research Questions</h1>
		<h2 class="ml-20 border-l-2 border-white p-4 text-xl">
			How did emotions impact the candidates to be chosen <br /> for the elections?
		</h2>
	</div>

	<div class="p-20">
		<div class="flex flex-row content-center">
			<figure class=" flex flex-col content-center border-r-2 border-b-2 border-accent">
				<!-- <img class="" src="{base}/image6.png" alt="Tone Counts Plot" /> -->
				<ToneBar />
				<figcaption class="p-2 text-center text-xs font-light">
					Figure 3. Tone counts across the entire dataset containing the sentiments of each tweet.
				</figcaption>
			</figure>

			<div class="w-1/2 border-2 p-3 text-right">
				<p class="text-lg">neutral is most common</p>
				<p>
					<br /> For Figure 3, most tweets showed a neutral tone, followed by enjoyment, contempt, 
					anger, disgust, sadness, surprise, and fear. This suggests that online discourse was 
					largely in the middle ground, balancing between negative and positive emotions, with 
					neutral tones possibly reflecting a tendency toward more factual or 
					evidence-based commentary.
				</p>
			</div>
		</div>

		<div class="flex flex-row">
			<div class="w-1/2 border-2 p-3 text-right">
				<p class="text-left text-lg">neutral is most common</p>
				<p class="text-left">
					<br />Figure 4 shows how tweet polarities are distributed across emotional tones. 
					Neutral polarity appears most often, especially with neutral and enjoyment tones, 
					while negative polarity is more associated with anger and contempt. This suggests 
					that tweets with balanced or mildly positive sentiment were more common, and 
					those with strong negative polarity tended to carry more intense emotions.
				</p>
			</div>

			<div>
				<figure class="flex flex-col border-t-2 border-l-2 border-accent">
					<!-- <img class="" src="{base}/image13.png" alt="Polarities Counts Plot" /> -->
					<PolaritiesBar />
					<figcaption class="p-2 text-center text-xs font-light">
						Figure 4. Counts of Polarities across the entire dataset containing the sentiments of
						each tweet, colored by the tweet's associated tone.
					</figcaption>
				</figure>
			</div>
		</div>
	</div>

	<p class="mr-18 p-3 text-right text-[30px] underline">heatmaps on polarity</p>
	<div class="p-20">
		<div class=" flex flex-row">
			<div class="w-1/2 border-b-2 border-l-2 border-accent p-5 text-right">
				<p class="text-left text-lg underline">emotions are conditional</p>
				<p class="text-left">
					<br />The heatmap in Figure 5 shows the emotional tones of tweets 
					mentioning senatorial candidates. Neutral is most common, especially 
					for Kiko Pangilinan and Bam Aquino, who also appear with enjoyment. 
					Imee Marcos has fewer mentions, showing neutral along with some anger and contempt. 
					Other candidates are linked with scattered tones, with fewer appearances of the other tones.
				</p>
			</div>

			<figure class="flex flex-col justify-center p-8">
				<img
					class="self-center-safe"
					src="{base}/image9.png"
					alt="Heatmap of Tone Instances for Winning Candidates"
				/>
				<figcaption class="p-3 text-center text-[10px] font-light">
					Figure 5. Heatmap of the amount of instances of tone in relation to the subset of winning
					senatorial candidates across all tweets.
				</figcaption>
			</figure>
		</div>

		<div class="flex flex-row">
			<div class="w-1/2 border-l-2 border-accent p-5 text-right">
				<p class="text-left text-lg underline">emotions are conditional</p>
				<p class="text-left">
					<br />Figure 6 presents a heatmap of emotional tones in tweets mentioning 
					partylists. For Duterte Youth, anger and contempt are most common, with 
					some neutral and enjoyment also appearing. Makabayan, ML, Akbayan, BBM, 
					Kabataan, Bayan Muna, Magdalo, PBBM, Patrol, ACT-CIS, and ACT Teachers are mostly 
					associated with neutral and enjoyment tones, showing fewer of the other tones. 
					The remaining mentioned partylists are characterized primarily by neutral tones.
				</p>
			</div>

			<figure class="flex flex-col justify-center p-8">
				<img
					class="self-center-safe"
					src="{base}/image2.png"
					alt="Heatmap of Tone Instances for All Candidates"
				/>
				<figcaption class="p-3 text-center text-xs font-light">
					Figure 6. Heatmap of the amount of instances of tone in relation to the partylists
					mentioned across all tweets.
				</figcaption>
			</figure>
		</div>
	</div>

	<h2 class="ml-20 border-l-2 border-accent p-4 text-xl">
		What are the critical proponents that shape the decisions of Filipino voters over support for a
		candidate?
	</h2>

	<div class=" p-15">
		<div class="mb-lg flex flex-row">
			<div class="w-1/2 border-r-2 border-b-2 border-accent p-5">
				<figure class="flex flex-col">
					<img
						class="self-center"
						src="{base}/image4.png"
						alt="Heatmap of Associated Words vs Average Polarity"
					/>
					<figcaption class="p-3 text-center text-[10px] font-light">
						Figure 8. A heatmap of the associated word of a tweet in relation to the mentioned <br
						/>
						senatorial candidate, with the heat being the average polarity of a user in the tweet.
					</figcaption>
				</figure>

				<div class="p-5 text-right">
					<p class="text-left text-lg underline">neutral is most common</p>
					<p class="text-left">
						<br />In the case that multiple candidates were mentioned in a tweet, a list will be
						returned containing the corresponding tone, polarity, and judgement per candidate
						mentioned in that tweet. The particular model,
						meta-llama/llama-4-maverick-17b-128e-instruct, was used for its balance between speed,
						price, and accuracy based on its benchmarks on analysis (Artificial Index, 2025).
					</p>
				</div>
			</div>

			<div class="w-1/2 border-b-2 border-accent">
				<figure class="flex flex-col">
					<img
						class="self-center"
						src="{base}/image8.png"
						alt="Heatmap of Associated Words vs Polarity"
					/>
					<figcaption class="p-3 text-center text-[10px] font-light">
						Figure 9. A heatmap of the associated word in a tweet in relation to the mentioned <br
						/>
						partylist, with the heat being the polarity of the said tweet.
					</figcaption>
				</figure>

				<div class="p-5 text-right">
					<p class="text-left text-lg underline">neutral is most common</p>
					<p class="text-left">
						<br />In the case that multiple candidates were mentioned in a tweet, a list will be
						returned containing the corresponding tone, polarity, and judgement per candidate
						mentioned in that tweet. The particular model,
						meta-llama/llama-4-maverick-17b-128e-instruct, was used for its balance between speed,
						price, and accuracy based on its benchmarks on analysis (Artificial Index, 2025).
					</p>
				</div>
			</div>
		</div>

		<div class="flex flex-row p-3">
			<figure class="flex flex-col justify-center">
				<img class="self-center-safe" src="{base}/image5.png" alt="Word Cloud Plot" />
				<figcaption class="text-center text-xs font-light">
					Figure 7. A word cloud of the most mentioned words or phrases across the entire Tweets
					Dataset.
				</figcaption>
			</figure>

			<div class=" max-w-1/2 p-5 text-right">
				<p class="text-left text-lg underline">neutral is most common</p>
				<p class="text-left">
					<br />In the case that multiple candidates were mentioned in a tweet, a list will be
					returned containing the corresponding tone, polarity, and judgement per candidate
					mentioned in that tweet. The particular model,
					meta-llama/llama-4-maverick-17b-128e-instruct, was used for its balance between speed,
					price, and accuracy based on its benchmarks on analysis (Artificial Index, 2025).
				</p>
			</div>
		</div>
	</div>

	<h2 class="ml-[80px] border-l-2 border-accent p-4 text-xl">
		How much did online social media sentiments influence actions <br /> over the elections?
	</h2>

	<div class="p-20">
		<div class="flex flex-row">
			<figure class="flex flex-col justify-center border-b-2 border-accent p-3">
				<img
					class="self-center-safe"
					src="{base}/image11.png"
					alt="Heatmap of Perceived Judgement and Senatorial Candidates"
				/>
				<figcaption class="p-3 text-center text-xs font-light">
					Figure 10. A heatmap of the perceived judgement of a user towards their mentioned
					senatorial candidate in a tweet, with the heat being the amount of instances of that
					judgement per candidate.
				</figcaption>
			</figure>

			<div class="max-w-1/2 border-b-2 border-l-2 border-accent p-5 text-right">
				<p class="text-left text-lg underline">neutral is most common</p>
				<p class="text-left">
					<br />In the case that multiple candidates were mentioned in a tweet, a list will be
					returned containing the corresponding tone, polarity, and judgement per candidate
					mentioned in that tweet. The particular model,
					meta-llama/llama-4-maverick-17b-128e-instruct, was used for its balance between speed,
					price, and accuracy based on its benchmarks on analysis (Artificial Index, 2025).
				</p>
			</div>
		</div>

		<div class="flex flex-row">
			<figure class="flex flex-col justify-center p-3">
				<img
					class="self-center-safe"
					src="{base}/image7.png"
					alt="Heatmap of Perceived Judgement and Partylists"
				/>
				<figcaption class="p-3 text-center text-[10px] font-light">
					Figure 11. A heatmap of the perceived judgement of a user towards their mentioned
					partylist in a tweet, with the heat being the amount of instances of that judgement per
					candidate.
				</figcaption>
			</figure>

			<div class="max-w-1/2 border-l-2 border-accent p-5 text-right">
				<p class="text-left text-lg underline">neutral is most common</p>
				<p class="text-left">
					<br />In the case that multiple candidates were mentioned in a tweet, a list will be
					returned containing the corresponding tone, polarity, and judgement per candidate
					mentioned in that tweet. The particular model,
					meta-llama/llama-4-maverick-17b-128e-instruct, was used for its balance between speed,
					price, and accuracy based on its benchmarks on analysis (Artificial Index, 2025).
				</p>
			</div>
		</div>
	</div>

	<h1 class="mb-[10px] text-center text-[30px] underline">candidate mentions</h1>
	<p class="mb-[50px] text-center">
		(The correlation tests done in the hypothesis testing earlier may also be used <br /> for this research
		question.)
	</p>

	<div>
		<div class="flex flex-row">
			<figure class="flex flex-col justify-center">
				<!-- <img
					class="self-center-safe"
					src="{base}/image12.png"
					alt="Pie Chart of Senatorial Candidates Mentions"
				/> -->
				<CandidatesPie />
				<figcaption class="p-3 text-center text-[10px] font-light">
					Figure 12. A pie chart showing the percentage of senatorial candidates mentioned in
					relation to the dataset (tweets containing mentioning a candidate), ordered by amount,
					candidates with less than 3 mentions or past the top 10 are marked as others.
				</figcaption>
			</figure>

			<div class="max-w-1/2 p-5 text-right">
				<p class="text-left text-lg underline">Kiko and Bam.</p>
				<p class="text-left">
					<br />Figure 12 shows the fractions of the mentions of senatorial candidates in the
					dataset. It is seen in Figure 12 that Kiko and Bam had dominated their social media
					prescence being followed by Heidi Mendoza Imee Marcos, and Bong Go. This may be from their
					poularity in social media, especially in X (Twitter), where a lot of individuals that post
					are the youth, which their campaign massively focuses on. These are then followed by Imee
					Marcos and Bong Go, who are also popular candidates, known negatively or positively in
					social media.
				</p>
			</div>
		</div>

		<div class="flex flex-row">
			<figure class="flex flex-col justify-center">
				<!-- <img
					class="self-center-safe"
					src="{base}/image10.png"
					alt="Pie Chart of Partylist Mentions"
				/> -->
				<PartylistsPie />
				<figcaption class="p-3 text-center text-[10px] font-light">
					Figure 13. A pie chart showing the percentage of partylists mentioned in relation to the
					dataset (tweets containing a mention of a partylist), ordered by amount. With partylists
					past the Top 10 being marked as 'others'.
				</figcaption>
			</figure>

			<div class="max-w-1/2 p-5 text-right">
				<p class="text-left text-lg underline">A whole third.</p>
				<p class="text-left">
					<br />Figure 13 shows the fractions of the partylists mentioned in the dataset. Where it
					is seen that Duterte Youth takes 32.2% of the chart, followed by Makabayan, ml, and
					Akbayan. The popularity of Duterte Youth may be attributed to the popularity of former
					president Rodrigo Roa Duterte, which had a huge following in social media, albeit
					controversial, taking in negative and positive emotions. The partylist that follow,
					Makabayan, Ml, and Akbayan, may be attributed to the rise of the Youth in social media,
					which these partylist heavily target, and are supported by, causing a great following.
				</p>
			</div>
		</div>
	</div>

	<h2 class="mt-[50px] ml-20 border-l-2 border-accent p-4 text-xl">
		Are we able to predict the influence of social media on nationwide elections?
	</h2>
	<p class="ml-20 p-10">To be answered in the modelling stage</p>

	<div class="bg-primary text-accent">
		<p class="p-lg text-center">references found at documentation.</p>
	</div>
</section>
