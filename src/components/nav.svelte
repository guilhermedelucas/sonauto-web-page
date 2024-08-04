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

	const links = [
		{ href: `${base}/monitoramento`, text: 'Monitoramento' },
		{ href: `${base}/automacao`, text: 'Automação' },
		{ href: `${base}/servicos`, text: 'Assistência' },
		{ href: `${base}/sobre`, text: 'Sobre nós' },
		{ href: `${base}/contato`, text: 'Contato' }
	];
</script>

<header class="flex justify-between p-6 bg-white shadow-md relative">
	<div class="md:container md:mx-auto w-full flex justify-between items-center">
		<a href="{base}/" class="flex items-center">
			<img
				class="max-w-[200px]"
				alt="Sonauto Segurança Eletrônica logomarca"
				src="{base}/sonauto-logo.png"
			/>
		</a>

		<!-- Burger Icon for Small Devices -->
		<button class="md:hidden p-2 text-red-700" on:click={toggleMenu}>
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
		<nav class="hidden md:flex">
			<ul class="flex space-x-6">
				{#each links.slice(0, -1) as { href, text }}
					<li>
						<a
							{href}
							class="hover:text-gray-600 hover-effect {currentPage === text ? 'active' : ''}"
							>{text}</a
						>
					</li>
				{/each}
			</ul>
		</nav>
		<button
			class="bg-red-700 hover:bg-red-800 text-white py-2 px-4 rounded transition hidden md:block"
		>
			<a href={links[links.length - 1].href}>{links[links.length - 1].text}</a>
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
				{#each links as { href, text }}
					<li><a {href} class="text-white text-3xl" on:click={closeMenu}>{text}</a></li>
				{/each}
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
