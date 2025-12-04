<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import { base } from '$app/paths';
</script>

<section id="about" class="mt-30 mb-10 flex flex-col items-center justify-center gap-4 align-middle">
	<h1 class="text-center font-[HomeVideoBold-R90Dv] text-7xl text-[55px]">About Us!</h1>
	<p class="text-center font-[HomeVideo-ABLG6G]">Meet the people behind the data mess.</p>
	<Button href="#top" size="sm" variant="outline" class="font-[HomeVideo-ABLG6G]"
		>Back to top</Button
	>
</section>

<section class="mx-auto max-w-6xl font-[HomeVideo-ABLG6G]">
	<div class="flex flex-row p-10">
		<img src="{base}/lance.jpg" class="w-1/2 border-2 object-cover" alt="Lance Joseph D. Padilla" />
		<div class="border-2 p-10">
			<h2 class="text-3xl">Hi! I'm Lance</h2>
			<h3>bs computer science | chill guy</h3>
			<p>
				<br />Trying to survive the harsh environment of computer science. Most of my time is spent
				finishing academic tasks so I can graduate sooner. Aside from that, I enjoy producing music
				and discovering new sounds.
			</p>
			<Button
				href="https://www.facebook.com/ssep1234#"
				size="sm"
				variant="default"
				target="_blank"
				class="align-left mt-5">Contact Me</Button
			>
		</div>
	</div>

	<div class="flex flex-row p-10">
		<div class="border-2 p-10">
			<h2 class="text-3xl">Hey, I'm Stephen!</h2>
			<h3>bs computer science | Developer | Minecraft builder | Stardew Valley farmer</h3>
			<p>
				<br />A student-journalist/data analyst with a passion for knowledge! You can find me
				running deep into projects integrating social sciences and natural sciences with technology.
				In my free time I love to play open-world Sandbox Games like Minecraft and Stardew Valley.
			</p>
			<Button
				href="https://www.facebook.com/S1j2G3#"
				size="sm"
				variant="default"
				target="_blank"
				class="align-left mt-5">Contact Me</Button
			>
		</div>
		<img
			src="{base}/stephen.jpg"
			class="w-1/2 border-2 object-cover"
			alt="Stephen James S. Gonda"
		/>
	</div>

	<div class="flex flex-row p-10">
		<img
			src="{base}/geraldine.jpg"
			class="w-1/2 border-2 object-cover"
			alt="Geraldine Abigail A. Badiola"
		/>
		<div class="border-2 p-10">
			<h2 class="text-3xl">Hellooo I'm Geraldine</h2>
			<h3>bs computer science | Terrarian | modern family enjoyer</h3>
			<p>
				<br />A standard npc that likes to spend time watching tv series. in my free time i like to
				dabble in design and play terria. my interests include k-pop and looking for new hobbies
				with my friends. if you like any of the things i mentioned we'd definitely get along!
			</p>
			<Button
				href="https://www.facebook.com/GeraldineBadiola#"
				size="sm"
				variant="default"
				target="_blank"
				class="align-left mt-5">Contact Me</Button
			>
		</div>
	</div>
</section>
