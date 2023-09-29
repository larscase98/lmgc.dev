<script lang="ts">
	import Icon from '@iconify/svelte';
</script>

<svelte:head>
	<title>lars case</title>
</svelte:head>

<div class="cont">
	<header>
		<h1 class="chromabb">lars case</h1>
		<div class="info">
			<h2 class="subtitle">web developer</h2>
			<div class="socials">
				<a href="https://github.com/larscase98" target="_blank" class="github"
					><Icon icon="mdi:github" width="22" /><span>github</span></a
				>
				<a href="mailto:lars@aloft.software" target="_blank" class="email"
					><Icon icon="mdi:email" width="22" /> <span>email me</span></a
				>
			</div>
		</div>
	</header>
</div>
<a href="/projects" class="ul text-2xl">projects</a>

<style lang="postcss">
	.cont {
		@apply grid grid-cols-2 gap-2 rounded-xl shadow-xl mb-4;
		@apply bg-gradient-to-b from-gray-900 to-gray-800;
	}

	header {
		@apply flex flex-col justify-start items-center p-4 rounded bg-transparent col-span-full;

		h1 {
			@apply text-center leading-tight text-5xl sm:text-6xl md:text-8xl text-gray-200 pb-4;
		}

		.info {
			@apply w-full flex flex-col sm:flex-row justify-between items-center px-1 pt-4 pb-1;
		}

		.subtitle {
			@apply text-center text-2xl sm:text-2xl md:text-3xl text-fuchsia-100;
			@apply pb-4 sm:pb-0;
		}
	}

	.socials {
		@apply flex flex-col justify-center items-center sm:items-end space-y-1;

		a {
			@apply flex flex-row justify-between items-center;
			@apply px-2 py-1 rounded bg-gray-600 shadow-sm;
			@apply hover:bg-gray-300 transition-colors duration-150;

			&.github {
				@apply hover:text-[#4078c0];
			}

			&.email {
				@apply hover:text-[#bd2c00];
			}

			span {
				@apply ml-1;
			}
		}
	}

	.chromabb {
		text-shadow: -2px -2px 2px rgba(251, 12, 12, 0.8), 3px 0px 3px rgba(52, 251, 12, 0.8),
			0px -2px 3px rgba(37, 92, 232, 0.8);
	}
</style>
