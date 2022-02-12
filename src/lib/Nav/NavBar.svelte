<script>
	import { tweened } from 'svelte/motion';
	import { cubicOut } from 'svelte/easing';
	import { fade } from 'svelte/transition';
	import Hamburger from '$lib/Nav/Hamburger.svelte';
	import Nav from '$lib/Nav/Nav.svelte';

	export let logo = '';
	export let navButtons = [];
	export let headerHeight = 32;
	export let width = 200;
	export let breakpoint = 768;

	let menuToggled = false;
	let windowWidth;
	let duration = 400;

	const x = tweened(200, { duration: duration, easing: cubicOut });
	const toggleMenu = () => {
		if (menuToggled) {
			x.set(200);
			menuToggled = false;
		} else {
			x.set(0);
			menuToggled = true;
		}
	};
</script>

<svelte:window bind:innerWidth={windowWidth} />

{#if windowWidth !== undefined}
	{#if windowWidth >= breakpoint}
		<div class="relative flex justify-between items-center w-full h-full">
			<a href="/#">
				<img id="nav-logo" src={logo} alt="VOID Development" class="h-10" />
			</a>
			<Nav {navButtons} />
		</div>
	{:else}
		<!-- Logo -->

		<div class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 cursor-pointer">
			<a href="/#">
				<img id="nav-logo" src={logo} alt="VOID Development" class="h-10" />
			</a>
		</div>
		<div>
			<!-- Hamburger Button -->

			<div
				on:click={toggleMenu}
				style={`height: ${headerHeight}`}
				class="flex justify-end pt-6 pr-0"
			>
				<Hamburger {menuToggled} />
			</div>

			<!-- Overlay -->

			{#if menuToggled}
				<div
					transition:fade={{ duration: duration }}
					on:click={toggleMenu}
					class="fixed left-0 w-screen h-screen bg-black/50 z-40"
				/>
			{/if}

			<!-- Mobile Menu -->

			<div
				on:click={toggleMenu}
				style="top: {headerHeight}; width: {width}px; transform: translateX({$x}px; transform-origin: 0 0)"
				class="absolute right-0 h-screen bg-gray-50 z-50"
			>
				<Nav {navButtons} />
			</div>
		</div>
	{/if}
{/if}
