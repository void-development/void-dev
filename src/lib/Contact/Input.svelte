<script>
	import { onMount } from 'svelte';

	export let required = false;
	export let disabled = false;
	export let name = 'label';
	export let type = 'text';
	export let value = 'value';

	onMount(() => {
		inputElement.type = type;
	});
</script>

<div>
	<label for="name" class="text-lg pb-1">
		{name}{#if required}<span class="text-red-500 font-bold"> *</span>{/if}
	</label>
	<input
		{name}
		id="name"
		class="w-full p-1 m-0 text-black text-base font-sans font-semibold border-2 border-gray-200 bg-white"
		bind:value
		{disabled}
		maxLength="100"
		{required}
	/>
</div>
