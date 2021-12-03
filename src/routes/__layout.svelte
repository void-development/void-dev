<script>
	import 'tailwindcss/tailwind.css';
</script>

<header
	class="flex justify-center items-center w-full h-24 px-8 bg-white border-b-2 sm:justify-start"
>
	<img src="/logo.svg" alt="Void Development Logo" class="object-scale-down w-48" />
</header>

<main>
	<slot />
</main>

<footer class="flex justify-center items-center w-full h-24 bg-white border-t-2">
	<p class="text-xl">Coded by VOID Development</p>
</footer>
