<div class="home">
	<nav class="navbar">
		<span class="logo">Altron</span>
		<div class="links">
			<a href="https://github.com/Shinji13/Altron" target="_blank"
				><i class="fa-brands fa-github" style="color: #3366ff;"></i></a
			>
			<a href="https://www.npmjs.com/package/@altron/altron" target="_blank"
				><i class="fa-brands fa-npm" style="color: #3366ff;"></i></a
			>
		</div>
	</nav>
	<section class="description">
		<h1>Power your apps with altron</h1>
		<p>Rich text editing made easy with the help of svelte components</p>
		<a href="https://github.com/Shinji13/Altron" target="_blank"><button>Get started now</button></a
		>
	</section>
	<div class="body">
		<h2>Feel free to take a tour</h2>
		<section class="sections">
			<span class="wrapper">
				<span class="section">
					<a href="/test">Live-test</a>
				</span>
			</span>
			<span class="wrapper">
				<span class="section">
					<a href="/example">Example</a>
				</span>
			</span>
			<span class="wrapper">
				<span class="section">
					<a href="/docs">Docs</a>
				</span>
			</span>
		</section>
	</div>
</div>

<style>
	.home {
		width: 100vw;
		height: 100vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		padding-top: 10px;
		gap: 10%;
	}
	.navbar {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding-inline: 30px;
	}
	.navbar .logo {
		font-family: 'Archivo', sans-serif;
		font-size: var(--h3);
		font-weight: bold;
		color: var(--primary800);
	}

	.navbar .links {
		display: flex;
		align-items: center;
		gap: 18px;
	}

	.navbar .links i {
		font-size: 2.3rem;
	}
	.description {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 20px;
	}
	.description h1 {
		text-align: center;
		font-family: 'Archivo', sans-serif;
		font-size: var(--huge);
	}
	.description p {
		color: color-mix(in srgb, gray 50%, var(--font) 30%);
		font-weight: bold;
		font-size: var(--h4);
		text-align: center;
	}
	.description button {
		cursor: pointer;
		width: fit-content;
		height: fit-content;
		background-color: var(--primary800);
		padding-inline: 24px;
		padding-block: 16px;
		border-radius: 6px;
		font-weight: bold;
		font-size: var(--body);
		color: var(--bg);
		outline: none;
		border: none;
	}
	.body {
		width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 20px;
	}
	.sections {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 30px;
	}
	.sections .wrapper {
		width: 8rem;
		aspect-ratio: 1/1;
		border-radius: 50%;
		background-color: transparent;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.sections .wrapper {
		border: 2px solid var(--primary800);
	}

	.sections .wrapper:hover .section {
		background-color: color-mix(in srgb, var(--primary800) 60%, white 0%);
	}

	.sections .section {
		width: 7rem;
		aspect-ratio: 1/1;
		border-radius: 50%;
		display: flex;
		justify-content: center;
		align-items: center;
		border: inherit;
		cursor: pointer;
		font-size: var(--h4);
		text-transform: uppercase;
	}
	@media screen and (width <768px) {
		.sections .section {
			width: 5.5rem;
		}
		.sections .wrapper {
			width: 6.5rem;
		}
		.home {
			gap: 16%;
		}
	}
</style>
