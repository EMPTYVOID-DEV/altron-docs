<script>
	import TextWriting from '$lib/components/handlers/textWriting.svelte';
	import Logo from '$lib/components/icons/logo.svelte';
</script>

<div class="homeWrapper">
	<div class="home">
		<nav class="navbar">
			<Logo />
			<div class="links">
				<a target="_blank" href="https://github.com/Shinji13/Altron">
					<i class="fa-brands fa-github" style="color: #ffffff;"></i>
				</a>
				<a target="_blank" href="https://www.npmjs.com/package/@altron/altron"
					><i class="fa-brands fa-npm" style="color: #ffffff;"></i></a
				>
			</div>
		</nav>
		<section class="body">
			<TextWriting text="Easy rich text editing with altron svelte component." />
			<div class="sections">
				<div class="sectionWrapper">
					<a href="/example" class="section"> Example </a>
				</div>
				<div class="sectionWrapper">
					<a href="/test" class="section">Live Test </a>
				</div>
				<div class="sectionWrapper">
					<a href="/docs/Altron/Introduction" class="section"> Docs </a>
				</div>
			</div>
		</section>
	</div>
</div>

<style>
	.homeWrapper {
		width: 100vw;
		height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		background-color: var(--primary100);
	}
	.home {
		width: 95%;
		height: 95%;
		display: flex;
		flex-direction: column;
		gap: 20%;
		background-image: url('/altronBgMobile.png');
		background-position: center;
		background-size: cover;
		border-radius: 12px;
		padding-top: 20px;
		padding-bottom: 40px;
	}
	.navbar {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding-inline: 40px;
	}
	.navbar .links {
		display: flex;
		align-items: center;
		gap: 20px;
	}
	.links i {
		font-size: 2.3rem;
	}
	.body {
		width: 100%;
		display: grid;
		grid-template-columns: 45% 45%;
		gap: 5%;
		padding-inline: 2.5%;
	}
	.body .sections {
		width: 100%;
		display: grid;
		grid-template-columns: repeat(2, auto);
		align-items: center;
		justify-items: center;
		gap: 5%;
	}
	.body .sectionWrapper {
		aspect-ratio: 1/1;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.section {
		width: 80%;
		aspect-ratio: 1/1;
		border-radius: 50%;
		border: inherit;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: var(--h4);
		font-weight: bold;
		background-color: color-mix(in srgb, var(--highlight) 15%, white 0%);
	}

	.section:hover {
		filter: contrast(3);
		background-color: color-mix(in srgb, var(--highlight) 35%, white 0%);
	}
	.sectionWrapper:nth-child(1) {
		border: 2px solid var(--primary800);
		--highlight: var(--primary800);
		width: 9rem;
	}
	.sectionWrapper:nth-child(2) {
		border: 2px solid var(--secondary800);
		--highlight: var(--secondary800);
		width: 10rem;
	}
	.sectionWrapper:nth-child(3) {
		border: 2px solid var(--svelte);
		--highlight: var(--svelte);
		grid-column: span 2;
		justify-self: center;
		width: 11rem;
	}

	@media screen and (width < 768px) {
		.home {
			width: 100%;
			height: 100%;
			background-size: contain;
			border-radius: 0;
			gap: 15%;
		}
		.navbar {
			padding-inline: 20px;
		}
		.body {
			display: flex;
			flex-direction: column;
			gap: 40px;
		}
	}
</style>
