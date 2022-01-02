<script>
	export let href;
	export let text;

	let wrapperClassList = 'h-8 md:h-full my-4 md:my-0 hover:border-0 md:hover:bg-gray-200';
	let textClassList =
		'flex justify-center items-center h-full w-full md:px-4 text-2xl text-rm-gray font-bold cursor-pointer';
</script>

<li class={wrapperClassList}>
	<a {href}>
		<span id={text + '-nav-button'} class={textClassList}>
			{text}
		</span>
	</a>
</li>
