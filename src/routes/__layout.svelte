<script>
	import 'tailwindcss/tailwind.css';
	import NavBar from '$lib/Nav/NavBar.svelte';

	let logo;
	let windowWidth;

	$: if (windowWidth < 640) {
		logo = '/logo.svg';
	} else {
		logo = '/logo-full-horizontal.svg';
	}

	let navButtons = [{ text: 'About', href: '/#about' }];
</script>

<svelte:window bind:innerWidth={windowWidth} />

<header
	class="fixed top-0 w-full h-24 px-8 bg-white border-b-2 border-gray-200 sm:justify-start sm:px-16"
>
	<div class="w-full h-24">
		<NavBar {logo} {navButtons} headerHeight="6rem" />
	</div>
</header>

<main class="mt-24 bg-gray-50">
	<slot />
</main>

<footer
	class="flex flex-col gap-2 justify-center items-center w-full p-8 bg-white border-t-2 border-gray-200 sm:flex-row sm:gap-0"
>
	<p class="mr-2 text-xl">Created by</p>
	<span class="w-60">
		<img src="/logo-full-horizontal.svg" alt="VOID Development" class="h-7" />
	</span>
</footer>
