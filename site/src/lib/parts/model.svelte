<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import { base } from '$app/paths';
</script>

<section
	id="model"
	class="mt-30 mb-10 flex flex-col items-center justify-center gap-4 align-middle"
>
	<h1 class="text-center font-[HomeVideoBold-R90Dv] text-7xl text-[55px]">The Model</h1>
	<p class="text-center font-[HomeVideo-ABLG6G]">Lets see what we can predict.</p>
	<Button href="#top" size="sm" variant="outline" class="font-[HomeVideo-ABLG6G]"
		>Back to top</Button
	>
</section>

<section class="mx-auto max-w-7xl font-[HomeVideo-ABLG6G]">
	<p class="mx-auto max-w-4xl">
		Now knowing that some categories have a correlation with a candidates votes, let's try to create
		a model for predicting a candidate's votes using the categories from the Sentiment Analysis.
	</p>
	<div class="p-20">
		<div class="mx-20 mb-30 flex flex-row text-right">
			<div class="flex-1 border-r-2 border-r-white">
				<h2 class="mb-10 text-left text-4xl">How did it perform?</h2>
				<div class="m-2 flex">
					<p class="mr-3 rounded-lg bg-[#d9d9d9] px-4 py-0.5 text-center text-lg text-[#190a2f]">
						R2 Score of
					</p>
					<p class="text-lg">0.6376646934020613</p>
				</div>

				<div class="m-2 flex">
					<p class="mr-3 rounded-lg bg-[#d9d9d9] px-4 py-0.5 text-center text-lg text-[#190a2f]">
						RMSE of
					</p>
					<p class="text-lg">2759968.114456545</p>
				</div>

				<h2 class="my-10 text-left text-4xl">What did we use?</h2>

				<div class="m-2 flex">
					<p class="mr-3 rounded-lg bg-[#d9d9d9] px-4 py-0.5 text-center text-lg text-[#190a2f]">
						Alpha of
					</p>
					<p class="text-lg">1.0</p>
				</div>

				<div class="m-2 flex">
					<p class="mr-3 rounded-lg bg-[#d9d9d9] px-4 py-0.5 text-center text-lg text-[#190a2f]">
						Model of
					</p>
					<p class="text-lg">Ridge Regression</p>
				</div>
			</div>

			<div class="flex w-1/2 flex-col">
				<p class="text-4xl">How did we make it?</p>
				<p class="mt-5 mb-5 ml-10">
					Knowing that some features have a correlation with a senatorial candidate's votes, we used
					a RidgeRegression model to fit our training data, settting X to all the features, and
					setting y to be the total votes of each candidate. We split our data into test and
					training sets to determine the metrics of the model later on. After fitting the model,
					with alpha an alpha set to 1.0, the model was used to predict the votes of each candidate
					in the test set, which gave the scores and errors seen on the left.
					<br /><br />
					Ridge regression was chosen for its ability to consider multicollinearity between features,
					which is more than apparent with our nutshell plot. And in terms of context, this 'makes sense'
					as Anger would be naturally correlated with a Negative Polarity, and an Infavor judgement would
					be negatively correlated with an OpposedTo judgement. With this, Ridge Regression was seen
					to be a better 'fit' for a model.
					<br /><br />
					Prior to picking our model, we had also tried a Lasso Model, as well as tried different alphas
					for our Ridge Regression, along with feature selection through RFE on sklearn. It was seen
					that the Ridge Regression with an alpha of 1.0 performed the best out of all the configurations
					and models that were tried.
				</p>
			</div>
		</div>
		<div class="mb-25 flex flex-row bg-accent inset-shadow-2xs">
			<div class="min-w-1/2 content-center">
				<p class="border-r-2 border-r-accent-foreground text-center text-[40px]">
					Modelling notebook
				</p>
			</div>
			<div class="p-6 text-right">
				The model was made and tested in this colab notebook.
				<br />
				<Button
					href="https://colab.research.google.com/drive/1igFTKKacm53S3qmDCLSjy3L2dwYCc4vw?usp=sharing"
					size="sm"
					variant="default"
					target="_blank"
					class="align-left m-5">Google Colab</Button
				>
			</div>
		</div>

		<div class="flex flex-row content-center">
			<figure class=" flex flex-col content-center border-r-2 border-b-2 border-accent">
				<img class="" src="{base}/model_coeff_s.png" alt="Model Coefficients" />
				<figcaption class="p-2 text-center text-xs font-light">
					Figure 14. Model Coefficients after using Ridge Regression to fit to the data.
				</figcaption>
			</figure>

			<div class="min-w-1/2 border-2 p-3 text-right">
				<p class="text-lg">Negative Prevails</p>
				<p>
					<br />After fitting the model, the following coefficents are now seen, with Anger having
					the highest positive coefficient, which closely matches what was seen in the nutshell
					plot, where Anger had the strongest positive correlation with a candidate's votes.
					Following that trend, Unsure also had a high positive coefficient. Suprisingly, OpposedTo
					has a negative coefficient, despite having a strong positive correlation earlier, this may
					be attributed to the train-test split, where a set of candidates with low OpposedTo values
					may have had low votes, leading to a negative coefficient. With Polarities, it is still
					seen that a candidate's average polarity has a negative coefficient, matching what was
					seen with the correlation in the nutshell plot.
				</p>
			</div>
		</div>

		<div class="flex flex-row">
			<div class="min-w-1/2 border-2 p-3 text-right">
				<p class="text-left text-lg">How does it perform?</p>
				<p class="text-left">
					<br />After the model was fitted, the test sets were fed onto it, and its predicted values
					from the X test set were compared to the actual y test values.
					<br /><br />
					This gave an R^2 value of ~0.63766469, showing that the model has a moderate fit to the data,
					indicating that the features used have an effect on a candidate's votes, and 'closely' matches
					the training data.
					<br />
					It may be seen that there are only 11 test points, attributed to the small set of candidates
					with social media prescence from the initial scraping done. In the future, a more thorough
					scrape shall be done to increase the dataset to have a better test for the model.
					<br /><br />
					This also have an RMSE of ~2759968.114456545, showing that there is a large error in the model's
					prediction in the millions, indicating that more data is still needed to train the model to
					do a better fit.
					<br />
					This high error may also be attributed to outliers in the data, especially with some candidates
					dominating with votes. This may also be a cause of the votes being in the millions, causing
					a similar error scale to be seen.
				</p>
			</div>

			<div>
				<figure class="flex flex-col border-t-2 border-l-2 border-accent">
					<img
						class=""
						src="{base}/model_scatter_s.png"
						alt="The Scatter Plot of Predicted vs Actual"
					/>
					<figcaption class="p-2 text-center text-xs font-light">
						Figure 15. Scatter Plot of Predicted Votes to Actual Votes after predicted using Ridge
						Regression to the test set.
					</figcaption>
				</figure>
			</div>
		</div>
	</div>
</section>
