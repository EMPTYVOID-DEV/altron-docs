<script lang="ts">
	import { goto } from '$app/navigation';
	import { Altron } from '@altron/altron';
	import type { Altron as altronType } from '@altron/altron';
	import { onMount } from 'svelte';
	import CloseIcon from '$lib/components/icons/closeIcon.svelte';
	import Code from '$lib/components/handlers/code.svelte';
	let editor: altronType = null;

	onMount(() => {
		editor.setData([
			{
				id: '2',
				name: 'header',
				data: {
					level: 1,
					text: 'Here You can Test the edit mode'
				}
			}
		]);
	});
</script>

<div class="example">
	<header>
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<!-- svelte-ignore a11y-no-static-element-interactions -->
		<span
			on:click={() => {
				goto('/');
			}}><CloseIcon /></span
		>
	</header>
	<section class="editor">
		<Altron
			bind:this={editor}
			processEmbedSrcs={(src) => {
				const a = src.split('/');
				a.splice(a.length - 1, 0, 'embed');
				return a.join('/').replace('watch?v=', '');
			}}
			blocksGap={'10px'}
			customCode={Code}
			primaryColor={'#3164ff'}
			secondaryColor={'#14c489'}
			bgColor={'#ffffff'}
			textColor={'#121212'}
			headerFont="'Montserrat', sans-serif"
			bodyFont="'Source Sans 3', sans-serif"
		/>
	</section>
</div>

<style>
	.example {
		width: 95vw;
		height: 100vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		padding-top: 20px;
		padding-left: 20px;
		gap: 40px;
	}
	header {
		width: 100%;
		display: flex;
	}
	header span {
		width: 42px;
		height: 42px;
		border-radius: 50%;
		border: 2px solid var(--primary800);
		display: flex;
		align-items: center;
		justify-content: center;
		cursor: pointer;
	}
	header span :global(path) {
		fill: var(--primary800);
	}
	header span:hover {
		background-color: var(--primary400);
	}

	.editor {
		width: 60%;
	}
	@media screen and (width < 768px) {
		.editor {
			width: 100%;
		}
	}
</style>
