<script>
	import 'tailwindcss/tailwind.css';
</script>

<header
	class="flex justify-center items-center w-full h-24 px-8 bg-white border-b-2 sm:justify-start sm:px-16"
>
	<img src="/logo-full-horizontal.svg" alt="Void Development Logo" class="object-scale-down w-80" />
</header>

<main class="p-8 sm:p-16">
	<slot />
</main>

<footer class="flex justify-center items-center w-full h-24 bg-white border-t-2">
	<p class="text-xl">Coded by VOID Development</p>
</footer>
