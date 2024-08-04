<script>
	import { base } from '$app/paths';

	let isOpen = false;
	export let currentPage = '';
	function toggleMenu() {
		isOpen = !isOpen;
	}

	function closeMenu() {
		isOpen = false;
	}
</script>

<header class="flex justify-between items-center p-6 bg-white shadow-md">
	<img class="max-w-[200px]" src="{base}/sonauto-logo.png" />
	<nav>
		<ul class="flex space-x-6">
			<li><a href="{base}/" class="hover:text-red-600 hover-effect active">Home</a></li>
			<li><a href="{base}/sobre" class="hover:text-gray-600 hover-effect">Sobre nós</a></li>
			<li><a href="{base}/clients" class="hover:text-gray-600 hover-effect">Clientes</a></li>
			<li>
				<a href="{base}/testimonial" class="hover:text-gray-600 hover-effect">Testimonials</a>
			</li>
			<li><a href="{base}/seguranca" class="hover:text-gray-600 hover-effect">Segurança</a></li>
		</ul>
	</nav>
	<button class="bg-red-600 hover:bg-red-800 text-white py-2 px-4 rounded transition"
		>Peça um orçamento</button
	>
</header>

<style lang="postcss">
	.hover-effect {
		@apply relative inline-block no-underline; /* Tailwind utilities for relative positioning and removing underline */
		color: inherit;
	}

	.hover-effect::after {
		@apply bg-red-600;
		content: '';
		position: absolute;
		width: 100%;
		transform: scaleX(0);
		height: 3px;
		bottom: -4px;
		left: 0;
		transform-origin: bottom right;
		transition: transform 0.25s ease-out;
	}

	.active::after {
		@apply bg-red-600;
		content: '';
		position: absolute;
		width: 100%;
		transform: scaleX(0);
		height: 3px;
		bottom: -4px;
		left: 0;
	}

	.hover-effect.active::after {
		transform: scaleX(1);
		transform-origin: bottom left;
		transition: none; /* Remove transition for active state */
	}

	.hover-effect:hover::after {
		@apply bg-red-600;
		transform: scaleX(1);
		transform-origin: bottom left;
		transition: transform 0.25s ease-out;
	}
</style>
