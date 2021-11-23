<script>
	import 'tailwindcss/tailwind.css';
</script>

<header class="flex justify-start items-center w-full h-24 px-4 border-b-2 sm:px-8">
	<p class="p-2 border-[5px] border-black text-xl font-semibold sm:text-3xl">
		<span class="font-light tracking-widest">VOID</span> <span class="tracking-widest">/</span> DEV
	</p>
</header>

<main>
	<slot />
</main>

<footer class="flex justify-center items-center w-full h-24 border-t-2">
	<p class="text-xl">Coded by VOID Development</p>
</footer>
