<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import { base } from '$app/paths';
</script>

<section
	id="model"
	class="mt-30 mb-10 flex flex-col items-center justify-center gap-4 align-middle"
>
	<h1 class="text-center font-[HomeVideoBold-R90Dv] text-7xl text-[55px]">Conclusion</h1>
	<p class="text-center font-[HomeVideo-ABLG6G]">In a nutshell?</p>
	<Button href="#top" size="sm" variant="outline" class="font-[HomeVideo-ABLG6G]"
		>Back to top</Button
	>
</section>

<section class="mx-auto max-w-7xl font-[HomeVideo-ABLG6G]">
	<p class="mx-auto max-w-4xl">
		Now knowing that some categories have a correlation with a candidates votes, let's try to create
		a model for predicting a candidate's votes using the categories from the Sentiment Analysis.
	</p>
</section>
