<script lang="ts">
	import type { PageProps } from './$types.js';
	import Button from '$lib/components/ui/button/button.svelte';
	import Particles from '$lib/components/ui/Particles.svelte';
	import { base } from '$app/paths';

	let { data }: PageProps = $props();
</script>

<section class="mt-10 mb-30 flex flex-col items-center justify-center gap-6 align-middle">
	<h1 class="text-center text-7xl font-bold">About Us</h1>
	<Button href="{base}/" size="sm" variant="secondary">Go Back Home</Button>
</section>
<div class="about-box">
	<a href="https://www.facebook.com/ssep1234#"
		><img src="{base}/lance.jpg" alt="Lance Joseph D. Padilla" class="profile-pic" /></a
	>
	<div class="about-text">
		<h2
			class="text-base font-semibold tracking-[-0.015em] text-balance text-white md:max-w-lg md:text-xl lg:text-3xl"
		>
			Lance Joseph D. Padilla
		</h2>
		<p class="text-base/6 text-neutral-200">Team Developer</p>
		<p class="text-base/6 text-neutral-200">
			“Never give up, for that is just the place and time that the tide will turn.”
		</p>
	</div>
</div>

<div class="about-box">
	<a href="https://www.facebook.com/S1j2G3"
		><img src="{base}/stephen.jpg" alt="Stephen James S. Gonda" class="profile-pic" /></a
	>
	<div class="about-text">
		<h2
			class="text-base font-semibold tracking-[-0.015em] text-balance text-white md:max-w-lg md:text-xl lg:text-3xl"
		>
			Stephen James S. Gonda
		</h2>
		<p class="text-base/6 text-neutral-200">Team Developer</p>
		<p class="text-base/6 text-neutral-200">“We can do better if we think about it.”</p>
	</div>
</div>

<div class="about-box">
	<a href="https://www.facebook.com/GeraldineBadiola/"
		><img src="{base}/geraldine.jpg" alt="Geraldine Abigail A. Badiola" class="profile-pic" /></a
	>
	<div class="about-text">
		<h2
			class="text-base font-semibold tracking-[-0.015em] text-balance text-white md:max-w-lg md:text-xl lg:text-3xl"
		>
			Geraldine Abigail A. Badiola
		</h2>
		<p class="text-base/6 text-neutral-200">Team Developer</p>
		<p class="text-base/6 text-neutral-200">
			“Strength does not come from physical capacity. It comes from an indomitable will.”
		</p>
	</div>
</div>

<Particles className="absolute inset-0 -z-10" refresh={true} />

<style>
	.about-box {
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: 1000px;
		background-color: rgb(53, 50, 50);
		border-radius: 15px;
		padding: 20px;
		margin: 20px auto;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
	}

	.about-text {
		flex: 1;
		text-align: left;
		margin-right: 30px;
	}

	.about-text h2 {
		margin: 0 0 10px 0;
		color: white;
		font-size: 20px;
		margin-left: 15px;
		font-family: 'HomeVideo-ABLG6G';
	}

	.about-text p {
		margin: 0;
		font-size: 14px;
		margin-left: 15px;
	}

	.profile-pic {
		width: 120px;
		height: 120px;
		border-radius: 50%;
		object-fit: cover;
		flex-shrink: 0;
	}


</style>
