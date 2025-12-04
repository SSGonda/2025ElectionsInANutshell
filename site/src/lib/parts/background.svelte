<script lang="ts">
	import WobbleCard from '$lib/components/ui/WobbleCard.svelte';
</script>

<div class="mx-auto mt-10 grid w-full max-w-6xl grid-cols-1 gap-4 lg:grid-cols-3">
	<WobbleCard
		containerClass="col-span-1 lg:col-span-2 h-full bg-pink-800 min-h-[500px] lg:min-h-[300px]"
	>
		<div class="max-w-xs">
			<h2
				class="text-left text-base font-semibold tracking-[-0.015em] text-balance text-white md:text-xl lg:text-3xl"
			>
				Background
			</h2>
			<p class="mt-4 text-left text-base/6 text-neutral-200">
				Held on May 12, 2025, Halalan 2025 is the midterm election situated in the Republic of the
				Philippines to determine the future officials to take hold of higher authoritarian decisions
				under the term of President Bongbong Marcos. 317 seats in the house of representatives, as
				well as 12 of the 24 seats in the senate were up for undertaking to form the congress
				(Wikipedia, 2025).
			</p>
		</div>
	</WobbleCard>
	<WobbleCard containerClass="col-span-1 min-h-[300px]">
		<h2
			class="max-w-80 text-left text-base font-semibold tracking-[-0.015em] text-balance text-white md:text-xl lg:text-3xl"
		>
			Research Questions.
		</h2>
		<ol class="mt-4 max-w-[26rem] text-left text-base/6 text-neutral-200">
			<li>
				How did emotions and user sentiments impact the candidates to be chosen for the elections?
			</li>
			<li>
				What are the critical proponents that shape the decisions of Filipino voters over support
				for a candidate?
			</li>
			<li>How much did online trolling submissions influence actions over the elections?</li>
			<li>Are we able to predict the influence of social media on nationwide elections?</li>
		</ol>
	</WobbleCard>
	<WobbleCard
		containerClass="col-span-1 lg:col-span-3 bg-blue-900 min-h-[500px] lg:min-h-[600px] xl:min-h-[300px]"
	>
		<div class="max-w-sm">
			<h2
				class="max-w-sm text-left text-base font-semibold tracking-[-0.015em] text-balance text-white md:max-w-lg md:text-xl lg:text-3xl"
			>
				Proposed Solution.
			</h2>
			<p class="mt-4 max-w-[26rem] text-left text-base/6 text-neutral-200">
				We propose to enhance the magnification of these effects in correlation to the results made
				by the elections to hopefully raise discussions on the relevance of critical thinking and
				decision making.
			</p>
		</div>
	</WobbleCard>
	<WobbleCard
		containerClass="col-span-1 lg:col-span-3 bg-blue-900 min-h-[500px] lg:min-h-[600px] xl:min-h-[300px]"
	>
		<div class="max-w-sm">
			<h2
				class="max-w-sm text-left text-base font-semibold tracking-[-0.015em] text-balance text-white md:max-w-lg md:text-xl lg:text-3xl"
			>
				Hypotheses.
			</h2>
			<p class="mt-4 max-w-[26rem] text-left text-base/6 text-neutral-200">
				Null<br />
				Social media sentiments have no significant level of influence on the likelihood of being elected
				a Candidate during the 2025 Philippine National and Local Elections.
				<br />
				Alternative<br />
				Social media sentiments have a significant level of influence on the likelihood of being elected
				a Candidate during the 2025 Philippine National and Local Elections.
			</p>
		</div>
	</WobbleCard>
</div>
