<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import ArrowRight from '@lucide/svelte/icons/arrow-right';
    import WordsPullUp from '$lib/components/ui/WordsPullUp.svelte';
</script>

<div>
	<main class="overflow-hidden">
		<div class="absolute inset-0 isolate hidden opacity-65 contain-strict lg:block">
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
								href="/"
								class="hover:bg-background dark:hover:border-t-border bg-muted group mx-auto flex w-fit items-center gap-4 rounded-full border p-1 pl-4 shadow-md shadow-zinc-950/5 transition-colors duration-300 dark:border-t-white/5 dark:shadow-zinc-950"
							>
								<span class="text-foreground text-sm">Find out more about the project here.</span>
								<span
									class="dark:border-background block h-4 w-0.5 border-l bg-white dark:bg-zinc-700"
								></span>

								<div
									class="bg-background group-hover:bg-muted size-6 overflow-hidden rounded-full duration-500"
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

						<h1
							class="mt-12">
                            <WordsPullUp
                                class="text-4xl font-bold tracking-[-0.02em] text-black dark:text-white md:text-7xl md:leading-[5rem]"
                                words="2025 Elections in a Nutshell."
                            />
						</h1>

						<p class="mx-auto mt-3 max-w-2xl text-lg text-balance">
							An overview on the effects and relationships of Social Media Exposure to the 2025 Philippine Midterm Election.
						</p>

						<div class="mt-7 flex flex-col items-center justify-center gap-2 md:flex-row">
							<div
								class="bg-foreground/10 border p-0.5"
								style="border-radius: calc(0.5rem + 0.125rem + 4px);"
							>
								<Button href="/" size="lg" class="rounded-xl px-5 text-base">
									<span class="text-nowrap">Our Datasets.</span>
								</Button>
							</div>
							<Button href="https://docs.google.com/document/d/1tlSUfIRb3os0wD-ZWfunGBFz90_re7mKh7p5uedNXUs/edit?usp=sharing" target="_blank" size="lg" variant="ghost" class="rounded-xl px-5">
								Documentation
							</Button>
						</div>
					</div>
				</div>

				<div class="relative mt-8 -mr-56 overflow-hidden px-2 sm:mt-12 sm:mr-0 md:mt-20">
					<div
						class="to-background absolute inset-0 z-10 bg-linear-to-b from-transparent from-35%"
					></div>
					<div
						class="ring-background bg-background relative mx-auto max-w-6xl overflow-hidden rounded-2xl border p-4 shadow-lg inset-shadow-2xs shadow-zinc-950/15 dark:inset-shadow-white/20"
					>
						<img
							class="bg-background relative hidden aspect-16/9 rounded-2xl dark:block"
							src="/hero.jpg"
							alt="A Filipino voter that casted their vote, from Rappler."
							width="1920"
							height="1080"
						/>
						<img
							class="border-border/25 relative z-2 aspect-16/9 rounded-2xl border dark:hidden"
							src="/hero.jpg"
							alt="A Filipino voter that casted their vote, from Rappler."
							width="1920"
							height="1080"
						/>
					</div>
				</div>
			</div>
		</section>
	</main>
</div>