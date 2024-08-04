<script>
	import { base } from '$app/paths';
	import Customers from '../components/sections/customers.svelte';
	import { useReveal } from '../lib/reveal';

	// Call the custom hook to handle reveal functionality
	useReveal();
</script>

<main class="bg-white">
	<section class="text-center py-16 bg-gradient-to-r from-red-50 to-white md:px-0 px-4">
		<h2 class="text-4xl font-bold mb-4">Lorem ipsum dolor sit amet.</h2>
		<p class="text-gray-600 mb-6">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis laudantium iusto consequatur
			tenetur temporibus tempore ea fugit, earum voluptate atque soluta, ducimus veniam ex illum?
		</p>
		<button class="bg-red-700 text-white py-2 px-4 rounded hover:bg-red-900">Lorem, ipsum...</button
		>
	</section>

	<section class="py-4 md:py-16 bg-white md:px-0 px-4">
		<div class="grid grid-cols-1 md:grid-cols-3 gap-6 max-w-4xl mx-auto">
			<div class="relative bg-gradient-to-r from-red-900 to-red-600 rounded-lg p-1 reveal">
				<div class="bg-white shadow-md rounded-lg p-6 text-center">
					<h3 class="text-3xl font-bold mb-2">R$83,729</h3>
					<p class="text-gray-600">Lorem, ipsum.</p>
					<p class="text-red-700 mt-4">+12.6%</p>
				</div>
			</div>
			<div class="relative bg-gradient-to-r from-red-900 to-red-600 rounded-lg p-1 reveal">
				<div class="bg-white shadow-md rounded-lg p-6 text-center">
					<h3 class="text-3xl font-bold mb-2">95%</h3>
					<p class="text-gray-600">Lorem, ipsum.</p>
					<p class="text-red-700 mt-4">Lorem ipsum dolor sit, amet consectetur adipisicing elit.</p>
				</div>
			</div>
			<div class="relative bg-gradient-to-r from-red-900 to-red-600 rounded-lg p-1 reveal">
				<div class="bg-white shadow-md rounded-lg p-6 text-center">
					<h3 class="text-3xl font-bold mb-2">2.5k+</h3>
					<p class="text-gray-600">Seguidores</p>
					<p class="text-red-700 mt-4">Lorem ipsum dolor sit, amet consectetur adipisicing elit.</p>
				</div>
			</div>
		</div>
	</section>

	<Customers />

	<section class="py-16 bg-gradient-to-r from-white to-red-50 reveal md:px-0 px-4">
		<div class="text-center max-w-4xl mx-auto">
			<h3 class="text-3xl font-bold mb-4 reveal">Lorem ipsum dolor sit amet.</h3>
			<p class="text-gray-600 mb-6 reveal">
				Lorem ipsum dolor, sit amet consectetur adipisicing elit. Culpa eum, fuga suscipit tempore
				hic recusandae sint sunt quod a blanditiis!.
			</p>
		</div>
	</section>

	<section class="py-16 bg-white md:px-0 px-4">
		<div class="text-center max-w-4xl mx-auto">
			<h3 class="text-3xl font-bold mb-4 reveal">Sobre nós</h3>
			<p class="text-gray-600 mb-6 reveal">
				Lorem ipsum dolor sit, amet consectetur adipisicing elit. Veniam porro suscipit quas
				perspiciatis sint, saepe architecto non doloribus officiis, rerum fuga sed repellat ad
				cumque aut molestiae dolor nihil aperiam?
			</p>
		</div>
	</section>
</main>
