<script>
	export let href;
</script>

<li class="h-8 my-4 md:h-full md:my-0 md:hover:pt-2 md:hover:border-b-8">
	<a {href}>
		<span
			class="flex justify-center items-center h-full w-full md:px-4 text-2xl text-rm-gray font-bold cursor-pointer"
		>
			<slot />
		</span>
	</a>
</li>
