<script lang="ts">
	import './../app.postcss';
</script>

<main>
	<slot />
</main>

<style lang="postcss">
	main {
		@apply w-full min-h-screen flex flex-col justify-center items-center p-2;
		@apply bg-gradient-to-b from-gray-800 to-gray-700;
	}
</style>
