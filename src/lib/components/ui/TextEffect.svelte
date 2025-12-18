<script lang="ts">
	import { onMount } from 'svelte';

	type PresetType = 'blur' | 'fade' | 'slide' | 'scale';
	type PerType = 'word' | 'char' | 'line';

	let {
		text,
		per = 'word',
		preset = 'fade',
		delay = 0,
		staggerDelay = 0.05,
		class: className = ''
	}: {
		text: string;
		per?: PerType;
		preset?: PresetType;
		delay?: number;
		staggerDelay?: number;
		class?: string;
	} = $props();

	let mounted = $state(false);

	onMount(() => {
		mounted = true;
	});

	const getSegments = (str: string, segmentType: PerType): string[] => {
		if (!str) return [];
		if (segmentType === 'line') {
			return str.split('\n');
		} else if (segmentType === 'word') {
			return str.split(/(\s+)/);
		} else {
			return str.split('');
		}
	};

	let segments = $derived(getSegments(text, per));
</script>

<span class="text-effect {className}">
	{#each segments as segment, i}
		<span
			class="text-effect-segment {preset}"
			class:visible={mounted}
			style="--delay: {delay + i * staggerDelay}s; --index: {i};"
		>{segment}</span>
	{/each}
</span>

<style>
	.text-effect {
		display: inline;
	}

	.text-effect-segment {
		display: inline-block;
		white-space: pre-wrap;
	}

	/* Blur preset */
	.text-effect-segment.blur {
		opacity: 0;
		filter: blur(12px);
		transition: opacity 0.4s ease-out, filter 0.4s ease-out;
		transition-delay: var(--delay);
	}
	.text-effect-segment.blur.visible {
		opacity: 1;
		filter: blur(0px);
	}

	/* Fade preset */
	.text-effect-segment.fade {
		opacity: 0;
		transition: opacity 0.4s ease-out;
		transition-delay: var(--delay);
	}
	.text-effect-segment.fade.visible {
		opacity: 1;
	}

	/* Slide preset */
	.text-effect-segment.slide {
		opacity: 0;
		transform: translateY(20px);
		transition: opacity 0.4s ease-out, transform 0.4s ease-out;
		transition-delay: var(--delay);
	}
	.text-effect-segment.slide.visible {
		opacity: 1;
		transform: translateY(0);
	}

	/* Scale preset */
	.text-effect-segment.scale {
		opacity: 0;
		transform: scale(0);
		transition: opacity 0.4s ease-out, transform 0.4s ease-out;
		transition-delay: var(--delay);
	}
	.text-effect-segment.scale.visible {
		opacity: 1;
		transform: scale(1);
	}
</style>
