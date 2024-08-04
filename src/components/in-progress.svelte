<script>
	import { base } from '$app/paths';
	import { onMount } from 'svelte';

	let currentPath = '';
	onMount(() => {
		const url = new URL(window.location.href);
		currentPath = url.pathname.replace(base, '');
	});
</script>

<main class="flex flex-grow items-center justify-center">
	<div class="bg-white p-8 text-center rounded-lg shadow-md w-full max-w-lg">
		<img src="{base}/wip.png" alt="Work in Progress" class="mx-auto mb-2 w-32 h-32 grayscale" />
		<h1 class="text-2xl font-bold text-gray-800 mb-4">Página em construção</h1>
		<p class="text-gray-600 mb-6">
			A página <span class="font-mono text-red-600">{currentPath}</span> está em desenvolvimento. Por
			favor, volte mais tarde!
		</p>
		<a
			href="{base}/"
			class="inline-block bg-red-700 text-white py-2 px-4 rounded hover:bg-red-800 transition"
			>Voltar para a página inicial</a
		>
	</div>
</main>

<style>
	main {
		background-color: #f3f4f6; /* Tailwind's gray-100 */
	}
</style>
