<script>
	import Github from '$lib/icons/github.svelte';
	import Twitch from '$lib/icons/twitch.svelte';
	import V4 from '$lib/icons/v4.svelte';
	import Youtube from '$lib/icons/youtube.svelte';
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';
	let show = false;
	onMount(() => {
		setTimeout(() => {
			show = true;
		}, 50);
	});
</script>

<div class="pointer-events-none -z-40 bg-black selection:opacity-0">
	<img src="/bg.jpg" class="-z-40 h-screen w-screen opacity-50" alt="" />
</div>
{#if show}
	<div
		transition:fade={{ duration: 300 }}
		class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 content-center items-center justify-center text-center selection:opacity-0"
	>
		<h1
			class="ppointe pointer-events-none mb-0 text-5xl font-thin tracking-widest text-[#76FF7A] md:text-9xl"
		>
			HVCsano
		</h1>
		<h2 class="pointer-events-none text-xl text-white md:text-3xl">- Csanó -</h2>
		<div class="mt-5 flex items-center justify-center gap-2 sm:gap-4 md:gap-8">
			<a href="https://github.com/HVCsano" target="_blank"
				><Github
					stilus="group"
					pstilus="group-hover:fill-[#76FF7A] duration-300 transition-all"
				/></a
			>
			<a href="https://youtube.com/@HVCsano" target="_blank"
				><Youtube
					stilus="group"
					pstilus="group-hover:fill-[#76FF7A] duration-300 transition-all"
				/></a
			>
			<a href="https://twitch.tv/HVCsano" target="_blank">
				<Twitch stilus="group" pstilus="group-hover:fill-[#76FF7A] duration-300 transition-all" />
			</a>
			<a href="https://v4.csano.hu" target="_blank">
				<V4 stilus="group" pstilus="group-hover:fill-[#76FF7A] duration-300 transition-all" />
			</a>
		</div>
	</div>
{/if}
