<script lang="ts">
	import type { Portrait } from '$lib/types/portrait.type';

	import Github from '../svgs/github.svelte';
	import Twitter from '../svgs/twitter.svelte';
	import Linkedin from '../svgs/linkedin.svelte';
	import Dot from './dot.svelte';

	export let portrait: Portrait;
</script>

<div>
	<div class="flex h-full flex-col items-center justify-between">
		<div class="relative inline-block">
			<img
				class="rounded-2xl grayscale"
				width="170"
				height="170"
				alt="photo of {portrait.name}"
				src={portrait.imgsrc}
			/>
			<Dot class="absolute -top-5 -left-8 -z-10 h-16 w-16" />
		</div>
		<div class="mt-2 font-bold text-important">{portrait.name}</div>
		<div class="mt-2 text-center text-xs">{portrait.role}</div>
		<div class="mt-2 text-xs">{portrait.company}</div>
		<div class="mt-3 flex justify-center gap-3">
			{#if portrait.githubLink}<a target="_blank" href={portrait.githubLink}> <Github /></a>{/if}
			{#if portrait.twitterLink}<a target="_blank" href={portrait.twitterLink}><Twitter /></a>{/if}
			{#if portrait.linkedinLink}<a target="_blank" href={portrait.linkedinLink}><Linkedin /></a
				>{/if}
		</div>
	</div>
</div>
