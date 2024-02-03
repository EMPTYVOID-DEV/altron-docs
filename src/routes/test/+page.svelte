<script lang="ts">
	import { goto } from '$app/navigation';
	import Altron from '@altron/altron/altron.svelte';
	import { componentMap } from '$lib/components/altron/index';
	import { exampleData } from '$lib/utils/consts';
	import BackIcon from '$lib/components/other/backIcon.svelte';
</script>

<div class="example">
	<header>
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<!-- svelte-ignore a11y-no-static-element-interactions -->
		<span
			on:click={() => {
				goto('/');
			}}><BackIcon /></span
		>
	</header>

	<section class="editor">
		<Altron
			acceptedEmbedSrcs={{
				description: 'The sources from youtube embeds are accepted.',
				rules: ['^https://www.youtube.com/embed/[a-zA-Z0-9_-]{11}$']
			}}
			codeBlockLanguages={[
				'c',
				'javascript',
				'svelte',
				'typescript',
				'csharp',
				'python',
				'php',
				'lua'
			]}
			{componentMap}
			intialData={exampleData}
			primaryColor={'#3164ff'}
			secondaryColor={'#14c489'}
			blocksGap="20px"
			bgColor={'#121212'}
			textColor={'#ffffff'}
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
		background-color: var(--primary100);
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
