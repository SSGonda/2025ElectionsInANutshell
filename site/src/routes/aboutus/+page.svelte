<script lang="ts">
	import type { PageProps } from './$types.js';
	import Button from '$lib/components/ui/button/button.svelte';
	import Particles from '$lib/components/ui/Particles.svelte';
	import { base } from '$app/paths';

	let { data }: PageProps = $props();
</script>

<section class="mt-30 mb-10 flex flex-col items-center justify-center gap-4 align-middle">
	<h1 class="text-center text-7xl font-[HomeVideoBold-R90Dv] text-[55px]">About Us!</h1>
	<p class="font-[HomeVideo-ABLG6G] text-center">Meet the people behind the data mess.</p>
	<Button href="{base}/" size="sm" variant="outline" class="font-[HomeVideo-ABLG6G]">Go Back Home</Button>
</section>

<section class="font-[HomeVideo-ABLG6G]">
	<div class="flex flex-row p-10">
	<img src="{base}/lance.jpg" class="w-100 h-100 border-2" alt="Lance Joseph D. Padilla"/>
	<div class="border-2 p-10">
		<h2 class="text-[30px]">Hi! I'm Lance</h2>
		<h3>bs computer science | from the philippines</h3>
		<p><br>In the case that multiple candidates were mentioned in a tweet, a list will be 
		returned containing the corresponding tone, polarity, and judgement per candidate 
		mentioned in that tweet. The particular model, meta-llama/llama-4-maverick-17b-128e-instruct, 
		was used for its balance between speed, price, and accuracy based on its benchmarks on analysis 
		(Artificial Index, 2025).</p>
		<Button href="https://www.facebook.com/ssep1234#" size="sm" variant="default" target="_blank" class="align-left mt-5">Contact Me</Button>
		</div>
	</div>

	<div class="flex flex-row p-10">
	<div class="border-2 p-10">
		<h2 class="text-[30px]">Hey, I'm Stephen!</h2>
		<h3>bs computer science | Developer | Minecraft builder | Stardew Valley farmer</h3>
		<p><br>A student-journalist/data analyst with a passion for knowledge! 
			You can find me running deep into projects integrating social sciences and natural 
			sciences with technology. In my free time I love to play open-world Sandbox Games 
			like Minecraft and Stardew Valley.
		</p>
		<Button href="https://www.facebook.com/S1j2G3#" size="sm" variant="default" target="_blank" class="align-left mt-5">Contact Me</Button>
	</div>
	<img src="{base}/stephen.jpg" class="w-100 h-100 border-2" alt="Stephen James S. Gonda"/>
	</div>
	
	<div class="flex flex-row p-10">
	<img src="{base}/geraldine.jpg" class="w-100 h-100 border-2" alt="Geraldine Abigail A. Badiola"/>
	<div class="border-2 p-10">
		<h2 class="text-[30px]">Hellooo I'm Geraldine</h2>
		<h3>bs computer science | Terrarian | modern family enjoyer</h3>
			<p><br>A standard npc that likes to spend time watching tv series. in my free time
			i like to dabble in design and play terria. my interests include k-pop and looking
			for new hobbies with my friends. if you like any of the things i mentioned we'd
			definitely get along!
		</p>
		<Button href="https://www.facebook.com/GeraldineBadiola#" size="sm" variant="default" target="_blank" class="align-left mt-5">Contact Me</Button>
		</div>
	</div>
	<Particles className="absolute inset-0 -z-10" refresh={true} />
	</section>
