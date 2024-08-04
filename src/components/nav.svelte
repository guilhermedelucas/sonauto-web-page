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

<header class="flex justify-between p-6 bg-white shadow-md relative">
	<div class="md:container md:mx-auto w-full flex justify-between items-center">
		<a href="{base}/" class="flex items-center">
			<img class="max-w-[200px]" src="{base}/sonauto-logo.png" />
		</a>

		<!-- Burger Icon for Small Devices -->
		<button class="lg:hidden p-2 text-red-700" on:click={toggleMenu}>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-8 w-8"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 6h16M4 12h16M4 18h16"
				/>
			</svg>
		</button>

		<!-- Navigation Menu -->
		<nav class="hidden lg:flex">
			<ul class="flex space-x-6">
				<li>
					<a
						href="{base}/"
						class="hover:text-red-600 hover-effect {currentPage === 'home' ? 'active' : ''}">Home</a
					>
				</li>
				<li>
					<a
						href="{base}/sobre"
						class="hover:text-gray-600 hover-effect {currentPage === 'sobre' ? 'active' : ''}"
						>Sobre nós</a
					>
				</li>
				<li>
					<a
						href="{base}/clients"
						class="hover:text-gray-600 hover-effect {currentPage === 'clientes' ? 'active' : ''}"
						>Clientes</a
					>
				</li>
				<li>
					<a
						href="{base}/contato"
						class="hover:text-gray-600 hover-effect {currentPage === 'contato' ? 'active' : ''}"
						>Contato</a
					>
				</li>
				<li>
					<a
						href="{base}/seguranca"
						class="hover:text-gray-600 hover-effect {currentPage === 'seguranca' ? 'active' : ''}"
						>Segurança</a
					>
				</li>
			</ul>
		</nav>
		<!-- Call to Action Button -->
		<button
			class="hidden lg:block bg-red-700 hover:bg-red-800 text-white py-2 px-4 rounded transition"
		>
			<a href="{base}/contato"> Peça um orçamento </a>
		</button>
	</div>

	<!-- Full-Screen Menu Overlay -->
	{#if isOpen}
		<div
			class="fixed inset-0 bg-red-950 bg-opacity-90 flex flex-col items-center justify-center z-50"
		>
			<button class="absolute top-4 right-4 text-white text-3xl" on:click={closeMenu}>
				&times;
			</button>
			<ul class="space-y-6">
				<li><a href="{base}/" class="text-white text-3xl" on:click={closeMenu}>Home</a></li>
				<li>
					<a href="{base}/sobre" class="text-white text-3xl" on:click={closeMenu}>Sobre nós</a>
				</li>
				<li>
					<a href="{base}/clients" class="text-white text-3xl" on:click={closeMenu}>Clientes</a>
				</li>
				<li>
					<a href="{base}/contato" class="text-white text-3xl" on:click={closeMenu}>Contato</a>
				</li>
				<li>
					<a href="{base}/seguranca" class="text-white text-3xl" on:click={closeMenu}>Segurança</a>
				</li>
			</ul>
		</div>
	{/if}
</header>

<style lang="postcss">
	.hover-effect {
		@apply relative inline-block no-underline; /* Tailwind utilities for relative positioning and removing underline */
		color: inherit;
	}

	.hover-effect::after {
		@apply bg-red-700;
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

	.hover-effect.active::after {
		transform: scaleX(1);
		transform-origin: bottom left;
		transition: none; /* Remove transition for active state */
	}

	.hover-effect:hover::after {
		@apply bg-red-700;
		transform: scaleX(1);
		transform-origin: bottom left;
		transition: transform 0.25s ease-out;
	}
</style>
