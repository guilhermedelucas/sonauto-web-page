<script>
	import { base } from '$app/paths';
	import { links } from '../lib/links';

	let isOpen = false;
	export let currentPage = '';
	let isAnimating = false;

	function toggleMenu() {
		if (isOpen) {
			isAnimating = true;
			setTimeout(() => {
				isOpen = false;
				isAnimating = false;
			}, 300); // Match the animation duration
		} else {
			isOpen = true;
		}
	}

	function closeMenu() {
		isAnimating = true;
		setTimeout(() => {
			isOpen = false;
			isAnimating = false;
		}, 300); // Match the animation duration
	}
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
			class="bg-red-700 hover:bg-red-800 text-white py-2 px-4 rounded transition hidden md:block {currentPage ===
			links[links.length - 1].text
				? 'active underline'
				: ''}"
		>
			<a href={links[links.length - 1].href}>{links[links.length - 1].text}</a>
		</button>
	</div>

	<!-- Full-Screen Menu Overlay -->
	{#if isOpen}
		<div
			class="fixed inset-0 bg-red-950 bg-opacity-90 flex flex-col items-center justify-center z-50 {isAnimating
				? 'animate-slide-out-left'
				: 'animate-slide-in-left'}"
		>
			<button class="absolute top-4 right-4 text-white text-5xl mr-4" on:click={closeMenu}>
				&times;
			</button>
			<ul class="space-y-6 -mt-12">
				{#each links as { href, text }}
					<li>
						<a
							{href}
							class="text-white text-3xl {currentPage === text ? 'active underline' : ''}"
							on:click={closeMenu}>{text}</a
						>
					</li>
				{/each}
			</ul>
		</div>
	{/if}
</header>

<style lang="postcss">
	@keyframes slide-in-left {
		from {
			transform: translateX(-100%);
		}
		to {
			transform: translateX(0);
		}
	}

	@keyframes slide-out-left {
		from {
			transform: translateX(0);
		}
		to {
			transform: translateX(-100%);
		}
	}

	.animate-slide-in-left {
		animation: slide-in-left 0.3s ease-out;
	}

	.animate-slide-out-left {
		animation: slide-out-left 0.3s ease-out;
	}

	.fixed {
		@apply bg-red-950 bg-opacity-90 flex flex-col items-center justify-center z-50;
		inset: 0;
	}

	.hover-effect {
		@apply relative inline-block no-underline;
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
		transition: none;
	}

	.hover-effect:hover::after {
		@apply bg-red-700;
		transform: scaleX(1);
		transform-origin: bottom left;
		transition: transform 0.25s ease-out;
	}
</style>
