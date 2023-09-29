<script lang="ts">
	import Icon from '@iconify/svelte';

	type Project = {
		title: string;
		link: string;
		blurb: string;
		techs: string[];
	};

	const p = (title: string, link: string, blurb: string, techs: string[]): Project => {
		return {
			title,
			link,
			blurb,
			techs
		};
	};

	const projects = [
		p(
			'aloft software homepage',
			'https://aloft.software',
			'Simple website i created for my freelance web business. Contact page saves form submissions to MongoDB.',
			['sk', 'tw', 'mongo']
		),
		p(
			'family network',
			'/missing-project',
			'Invite-only social network designed to be the center of communication for a family. Auth, rich text posts, image uploads, comments, and user profiles.',
			['ex', 'sv', 'tw', 'mongo']
		)
	];
</script>

<svelte:head>
	<title>lars case | projects</title>
</svelte:head>

<div class="w-full flex flex-col justify-center items-center space-y-2">
	<a href="/">
		<Icon icon="icon-park-outline:left-two" width="32" />
	</a>

	<h1 class="pt-4 pb-8">projects</h1>

	<div class="projects">
		{#each projects as p}
			<section>
				<h3>
					<a href={p.link} target={p.link.startsWith('http') ? '_blank' : ''} class="ul"
						>{p.title}</a
					>
				</h3>
				<p>{p.blurb}</p>

				{#if p.techs.length > 0}
					<div class="techs">
						{#each p.techs as t}
							<div class="flex flex-row justify-center items-start space-x-2 py-1">
								{#if t === 'sv'}
									<Icon icon="logos:svelte-icon" width="22" aria-label="Svelte" />
									<span class="text-orange-400">Svelte</span>
								{:else if t === 'sk'}
									<Icon icon="skill-icons:svelte" width="24" aria-label="SvelteKit" />
									<span class="text-orange-500">SvelteKit</span>
								{:else if t === 'tw'}
									<Icon icon="skill-icons:tailwindcss-light" width="22" aria-label="TailwindCSS" />
									<span class="text-sky-300">TailwindCSS</span>
								{:else if t === 'ex'}
									<Icon icon="skill-icons:expressjs-light" width="22" aria-label="ExpressJS" />
									<span class="text-gray-300">Express.js</span>
								{:else if t === 'mongo'}
									<Icon icon="skill-icons:mongodb" width="22" aria-label="MongoDB" />
									<span class="text-green-500">MongoDB</span>
								{/if}
							</div>
						{/each}
					</div>
				{/if}
			</section>
		{/each}
	</div>
</div>

<style lang="postcss">
	.projects {
		@apply grid grid-cols-1 md:grid-cols-2 gap-4 w-11/12 md:w-5/6 lg:w-3/4;
	}

	section {
		@apply flex flex-col justify-around items-start space-y-2 p-4 rounded bg-gray-800;
		@apply hover:bg-gray-900 transition-all duration-300;
	}

	.techs {
		@apply w-full grid grid-cols-1 sm:grid-cols-2 place-items-center;
		@apply bg-gray-700 rounded-lg shadow-lg px-1 py-2;
	}
</style>
