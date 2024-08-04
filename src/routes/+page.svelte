<script>
	import { base } from '$app/paths';
	import Customers from '../components/sections/customers.svelte';
	import { useReveal } from '../lib/reveal';

	// Call the custom hook to handle reveal functionality
	useReveal();
</script>

<main class="bg-white">
	<section class="text-center py-16 bg-gradient-to-r from-red-50 to-white">
		<h2 class="text-4xl font-bold mb-4">Find a Better Solution for your Business</h2>
		<p class="text-gray-600 mb-6">
			From debt consolidation to your dream getaway, find a loan that meets your needs.
		</p>
		<button class="bg-red-700 text-white py-2 px-4 rounded hover:bg-red-900">Explore More</button>
	</section>

	<section class="py-16 bg-white">
		<div class="grid grid-cols-1 md:grid-cols-3 gap-6 max-w-4xl mx-auto">
			<div class="relative bg-gradient-to-r from-red-900 to-red-600 rounded-lg p-1 reveal">
				<div class="bg-white shadow-md rounded-lg p-6 text-center">
					<h3 class="text-3xl font-bold mb-2">$83,729</h3>
					<p class="text-gray-600">New Leads</p>
					<p class="text-red-700 mt-4">+12.6%</p>
				</div>
			</div>
			<div class="relative bg-gradient-to-r from-red-900 to-red-600 rounded-lg p-1 reveal">
				<div class="bg-white shadow-md rounded-lg p-6 text-center">
					<h3 class="text-3xl font-bold mb-2">95%</h3>
					<p class="text-gray-600">Positive Feedback</p>
					<p class="text-red-700 mt-4">We strongly believe that successful content marketing</p>
				</div>
			</div>
			<div class="relative bg-gradient-to-r from-red-900 to-red-600 rounded-lg p-1 reveal">
				<div class="bg-white shadow-md rounded-lg p-6 text-center">
					<h3 class="text-3xl font-bold mb-2">2.5k+</h3>
					<p class="text-gray-600">Insta Followers</p>
					<p class="text-red-700 mt-4">We strongly believe that successful content marketing</p>
				</div>
			</div>
		</div>
	</section>

	<Customers />

	<section class="py-16 bg-gradient-to-r from-white to-red-50 reveal">
		<div class="text-center max-w-4xl mx-auto">
			<h3 class="text-3xl font-bold mb-4 reveal">Our Progress & Marketing Analysis</h3>
			<p class="text-gray-600 mb-6 reveal">
				And produce say the ten moments parties. Simple innate summer fat appear basket his desire
				joy. Outward clothes promise at gravity do excited.
			</p>
		</div>
	</section>

	<section class="py-16 bg-white">
		<div class="text-center max-w-4xl mx-auto">
			<h3 class="text-3xl font-bold mb-4 reveal">ABOUT US</h3>
			<p class="text-gray-600 mb-6 reveal">
				We provide any for travelling assistance indulgence the unpleasing. Not thoughts all
				exercise blessing. Indulgence way everything joy alteration boisterous the attachment. Party
				we years to order allow asked of.
			</p>
		</div>
	</section>
</main>
