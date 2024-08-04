<script>
	import '../app.css';
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	import { base } from '$app/paths';
	import Nav from '../components/nav.svelte';
	import Footer from '../components/footer.svelte';

	let currentPage = 'home';

	$: {
		const path = $page.url.pathname;

		if (path === `${base}/`) {
			currentPage = 'home';
		} else if (path.startsWith(`${base}/about`)) {
			currentPage = 'about';
		} else if (path.startsWith(`${base}/services`)) {
			currentPage = 'services';
		} else if (path.startsWith(`${base}/contato`)) {
			currentPage = 'contato';
		}
	}
</script>

<svelte:head>
	<title>Law Consulting Services - Regulatory Compliance, Legal Consultation</title>
	<meta
		name="description"
		content="Moai Expert law consulting services including regulatory compliance, legal consultation, contract review, risk management, and litigation support."
	/>
	<meta
		name="keywords"
		content="law consulting, regulatory compliance, legal consultation, contract review, risk management, litigation support"
	/>
</svelte:head>

<div class="flex flex-col min-h-screen font-roboto text-gray-700">
	<Nav {currentPage} />
	<!-- <Banner
		description={bannerDescription}
		title={bannerTitle}
		imgSrc={bannerImgSrc}
		linkText={bannerLinkText}
		link={bannerLink}
	/> -->

	<main class="flex-grow">
		<slot />
	</main>

	<Footer />
</div>
