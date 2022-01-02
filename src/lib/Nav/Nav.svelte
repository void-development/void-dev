<script>
	import NavButton from '$lib/Nav/NavButton.svelte';
	export let navButtons = [];
</script>

<nav class="w-full md:w-auto h-full">
	<ul id="nav-list" class="flex flex-col md:flex-row items-center h-full">
		{#each navButtons as navButton}
			<NavButton text={navButton.text} href={navButton.href} />
		{/each}
	</ul>
</nav>
