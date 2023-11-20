<script lang="ts">
	import { quintIn } from 'svelte/easing';
	export let text = '';
	function write(node: HTMLSpanElement, { speed }: { speed: number }) {
		const duration = node.textContent?.length! / (speed * 0.001);
		const text = node.textContent;
		return {
			delay: 100,
			easing: quintIn,
			duration,
			tick: (t: number) => {
				let i = Math.trunc(t * node.textContent?.length!);
				node.textContent = text?.slice(0, i)!;
			}
		};
	}
</script>

<span>{text}</span>

<style>
	span {
		font-size: var(--huge);
		font-weight: bold;
		font-family: Archivo, sans-serif;
	}
</style>
