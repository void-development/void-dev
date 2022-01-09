<script>
	export let disabled = false;
	export let onClick = undefined;
</script>

<button
	type="button"
	{disabled}
	on:click={onClick}
	class="
  block
  p-2
  text-white 
  text-xl 
  font-bold
  cursor-pointer
  bg-black
  hover:bg-white
  hover:text-black
  hover:p-1
  hover:border-4
  hover:border-black"
>
	<span><slot /></span>
</button>
