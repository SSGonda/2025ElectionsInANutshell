<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import ArrowRight from '@lucide/svelte/icons/arrow-right';
	import WordsPullUp from '$lib/components/ui/WordsPullUp.svelte';
	import Particles from '$lib/components/ui/Particles.svelte';
	import { base } from '$app/paths';
	import WobbleCard from '$lib/components/ui/WobbleCard.svelte';
</script>

<div>
	<main class="overflow-hidden">
		<div class="absolute inset-0 isolate -z-20 hidden opacity-65 contain-strict lg:block">
			<div
				class="absolute top-0 left-0 h-320 w-140 -translate-y-87.5 -rotate-45 rounded-full bg-[radial-gradient(68.54%_68.72%_at_55.02%_31.46%,hsla(0,0%,85%,.08)_0,hsla(0,0%,55%,.02)_50%,hsla(0,0%,45%,0)_80%)]"
			></div>
			<div
				class="absolute top-0 left-0 h-320 w-60 [translate:5%_-50%] -rotate-45 rounded-full bg-[radial-gradient(50%_50%_at_50%_50%,hsla(0,0%,85%,.06)_0,hsla(0,0%,45%,.02)_80%,transparent_100%)]"
			></div>
			<div
				class="absolute top-0 left-0 h-320 w-60 -translate-y-87.5 -rotate-45 bg-[radial-gradient(50%_50%_at_50%_50%,hsla(0,0%,85%,.04)_0,hsla(0,0%,45%,.02)_80%,transparent_100%)]"
			></div>
		</div>
		<section>
			<div class="relative pt-24 md:pt-36">
				<div
					class="absolute inset-0 -z-10 size-full [background:radial-gradient(125%_125%_at_50%_100%,transparent_0%,var(--color-background)_75%)]"
				></div>
				<div class="mx-auto max-w-7xl px-6">
					<div class="text-center sm:mx-auto lg:mt-0 lg:mr-auto">
						<div>
							<a
								href="https://docs.google.com/document/d/1IjmjmYrjMhwYYxZNAdXBEPlILsOEzoj4zs2tUN7Ju68/edit?usp=sharing"
								target="_blank"
								class="group mx-auto flex w-fit items-center gap-4 rounded-full border bg-muted p-1 pl-4 shadow-md shadow-zinc-950/5 transition-colors duration-300 hover:bg-background dark:border-t-white/5 dark:shadow-zinc-950 dark:hover:border-t-border"
							>
								<span class="text-sm text-foreground">Find out more about the project here.</span>
								<span
									class="block h-4 w-0.5 border-l bg-white dark:border-background dark:bg-zinc-700"
								></span>

								<div
									class="size-6 overflow-hidden rounded-full bg-background duration-500 group-hover:bg-muted"
								>
									<div
										class="flex w-12 -translate-x-1/2 duration-500 ease-in-out group-hover:translate-x-0"
									>
										<span class="flex size-6">
											<ArrowRight class="m-auto size-3" />
										</span>
										<span class="flex size-6">
											<ArrowRight class="m-auto size-3" />
										</span>
									</div>
								</div>
							</a>
						</div>

						<div>
							<h1 class="mt-12">
								<WordsPullUp
									class="text-4xl font-bold tracking-[-0.02em] text-black md:text-7xl md:leading-[5rem] dark:text-white"
									words="2025 Elections in a Nutshell."
								/>
							</h1>

							<p class="mx-auto mt-3 max-w-2xl text-lg text-balance">
								An overview on the effects and relationships of Social Media Exposure to the 2025
								Philippine Midterm Election.
							</p>
							<Particles className="absolute inset-0 -z-10" refresh={true} />
						</div>

						<div class="mt-7 flex flex-col items-center justify-center gap-2 md:flex-row">
							<div
								class="border bg-foreground/10 p-0.5"
								style="border-radius: calc(0.5rem + 0.125rem + 4px);"
							>
								<Button
									href="{base}/datasets"
									size="lg"
									class="rounded-xl px-5 text-base"
								>
									<span class="text-nowrap">Our Datasets.</span>
								</Button>
							</div>
							<Button
								href="https://docs.google.com/document/d/1tlSUfIRb3os0wD-ZWfunGBFz90_re7mKh7p5uedNXUs/edit?usp=sharing"
								target="_blank"
								size="lg"
								variant="ghost"
								class="rounded-xl px-5"
							>
								Documentation
							</Button>
						</div>
					</div>
				</div>

				<div class="mt-30 mx-auto grid w-full max-w-6xl grid-cols-1 gap-4 lg:grid-cols-3">
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
								Held on May 12, 2025, Halalan 2025 is the midterm election situated in the Republic of the Philippines to determine the future officials to take hold of higher authoritarian decisions under the term of President Bongbong Marcos. 317 seats in the house of representatives, as well as 12 of the 24 seats in the senate were up for undertaking to form the congress (Wikipedia, 2025). 
							</p>
						</div>
					</WobbleCard>
					<WobbleCard containerClass="col-span-1 min-h-[300px]">
						<h2
							class="max-w-80 text-left text-base font-semibold tracking-[-0.015em] text-balance text-white md:text-xl lg:text-3xl"
						>
							Research Questions.
						</h2>
						<!-- <p class="mt-4 max-w-[26rem] text-left text-base/6 text-neutral-200">
						</p> -->
							<ol>
								<li>How did emotions and user sentiments impact the candidates to be chosen for the elections?</li>
								<li>What are the critical proponents that shape the decisions of Filipino voters over support for a candidate?</li>
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
								We propose to enhance the magnification of these effects in correlation to the results made by the elections to hopefully raise discussions on the relevance of critical thinking and decision making.
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
								Null<br>
								Social media sentiments have no significant level of influence on the likelihood of being elected a Candidate during the 2025 Philippine National and Local Elections.
								<br>
								Alternative<br>
								Social media sentiments have a significant level of influence on the likelihood of being elected a Candidate during the 2025 Philippine National and Local Elections.
							</p>
						</div>
					</WobbleCard>
				</div>

				<div class="relative mt-8 -mr-56 overflow-hidden px-2 sm:mt-12 sm:mr-0 md:mt-20">
					<div
						class="absolute inset-0 z-10 bg-linear-to-b from-transparent from-35% to-background"
					></div>
					<div
						class="relative mx-auto max-w-6xl overflow-hidden rounded-2xl border bg-background p-4 shadow-lg inset-shadow-2xs shadow-zinc-950/15 ring-background dark:inset-shadow-white/20"
					>
						<img
							class="relative hidden aspect-16/9 rounded-2xl bg-background dark:block"
							src="{base}/hero.jpg"
							alt="A Filipino voter that casted their vote, from Rappler."
							width="1920"
							height="1080"
						/>
						<img
							class="relative z-2 aspect-16/9 rounded-2xl border border-border/25 dark:hidden"
							src="{base}/hero.jpg"
							alt="A Filipino voter that casted their vote, from Rappler."
							width="1920"
							height="1080"
						/>
					</div>
				</div>
				<p class="text-white align-middle text-center">Image Source: Rappler</p>
			</div>
		</section>

		<section></section>
	</main>
</div>
