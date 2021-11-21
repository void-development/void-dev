<script>
	import 'tailwindcss/tailwind.css';
</script>

<header class="flex justify-start items-center w-full h-16 px-4 border-b-2 sm:px-8">
	<p class="text-3xl font-semibold"><span class="font-light tracking-widest">VOID</span> / DEV</p>
</header>

<main>
	<slot />
</main>

<footer class="flex justify-center items-center w-full h-16 border-t-2">
	<p class="text-xl">Coded by VOID Development</p>
</footer>
