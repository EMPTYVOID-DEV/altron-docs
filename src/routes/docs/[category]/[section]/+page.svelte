<script lang="ts">
	import { Main } from 'sveltedocsmaker';
	import { page } from '$app/stores';
	import Logo from '$lib/components/icons/logo.svelte';

	$: data = $page.data as {
		md: string;
		toc: {
			degree: number;
			name: string;
		}[];
	};

	const sectionMap = new Map([
		['Altron', ['Introduction', 'Data structure', 'Getting started', 'What next']],
		['Usage', ['Customization', 'Utils', 'Events', 'Types', 'View mode', 'Notes', 'Props']]
	]);
</script>

<Main
	{data}
	sectionsMap={sectionMap}
	pathname={$page.url.pathname}
	logo={Logo}
	navlinks={[
		{
			label: 'Home',
			href: '/'
		},
		{
			label: 'Example',
			href: '/example'
		},
		{
			label: 'Live test',
			href: '/test'
		}
	]}
	githubLink="https://github.com/Shinji13/Altron"
	npmLink="https://www.npmjs.com/package/@altron/altron"
	navBarHeight={80}
	headingFont="'Montserrat', sans-serif"
	bodyFont="'Source Sans 3', sans-serif"
	darkPrimary={'#3164ff'}
	darkBgColor={'#121212'}
	darkFontColor={'#ffffff'}
	lightPrimary={'#cc3300'}
	lightBgColor={'#ffffff'}
	lightFontColor={'#121212'}
/>
