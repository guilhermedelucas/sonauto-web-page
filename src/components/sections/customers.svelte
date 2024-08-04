<script>
	import { base } from '$app/paths';
	import { useReveal } from '../../lib/reveal';
	// List of customer logos
	let customerLogos = [
		`${base}/logo1.jpg`,
		`${base}/logo2.jpg`,
		`${base}/logo3.jpg`,
		`${base}/logo4.png`,
		`${base}/logo5.jpg`
		// Add more logos as needed
	];

	useReveal();
</script>

<section class="container mx-auto my-12 px-4">
	<h2 class="text-3xl font-bold text-center mb-6 reveal">Clientes Satisfeitos</h2>
	<div class="flex flex-wrap items-center justify-center gap-4">
		{#each customerLogos as logo}
			<div class="flex items-center justify-center p-2 reveal">
				<img
					src={logo}
					alt="Customer Logo"
					class="max-w-full max-h-24 object-contain grayscale transition duration-300 ease-in-out hover:grayscale-0"
				/>
			</div>
		{/each}
	</div>
</section>
