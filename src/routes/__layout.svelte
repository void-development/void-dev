<script>
	import '../app.css';
	import NavBar from '$lib/Nav/NavBar.svelte';

	let logo;
	let windowWidth;

	$: if (windowWidth < 640) {
		logo = '/logo.svg';
	} else {
		logo = '/logo-full-horizontal.svg';
	}

	let navButtons = [
		{ text: 'About', href: '/#' },
		{ text: 'Contact', href: '/#contact' }
	];
</script>

<svelte:window bind:innerWidth={windowWidth} />

<header class="fixed top-0 w-full h-24 z-50 sm:justify-start">
	<div
		class="absolute top-0 w-full h-24 px-8 backdrop-blur-sm border-b-2 border-gray-200 z-40 md:px-16 lg:px-32"
	>
		<NavBar {logo} {navButtons} headerHeight="6rem" />
	</div>
	<div
		id="header-blur"
		class="absolute top-0 w-full h-24 m-0 p-0 bg-white opacity-100 z-30 md:opacity-90"
	/>
</header>

<main class="mt-24 bg-gray-50 font-open-sans">
	<div id="header-blur" class="fixed top-0 w-full h-24" />
	<slot />
</main>

<footer
	class="flex flex-col gap-2 justify-center items-center w-full p-8 bg-white border-t-2 border-gray-200 sm:flex-row sm:gap-0"
>
	<p class="mr-2 text-lg">Created by</p>
	<span class="w-60">
		<img src="/logo-full-horizontal.svg" alt="VOID Development" class="h-8" />
	</span>
</footer>
