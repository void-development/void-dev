<script>
	import { tweened } from 'svelte/motion';
	import { sineOut } from 'svelte/easing';
	import { fade } from 'svelte/transition';
	import { beforeUpdate } from 'svelte';

	export let menuToggled;

	let duration = 200;
	let fadeDuration = 150;

	const xBarWidth = tweened(32, { duraiton: duration, easing: sineOut });

	const topBarRotation = tweened(0, { duration: duration, easing: sineOut });
	const bottomBarRotation = tweened(0, { duration: duration, easing: sineOut });

	beforeUpdate(() => {
		if (menuToggled === true) {
			topBarRotation.set(-45);
			bottomBarRotation.set(45);
			xBarWidth.set(28);
		} else {
			topBarRotation.set(0);
			bottomBarRotation.set(0);
			xBarWidth.set(32);
		}
	});
</script>

<div id="menu-wrapper">
	<div
		class="bar"
		id="bar1"
		style="width: {$xBarWidth}px; transform: rotate({$topBarRotation}deg)"
	/>
	{#if !menuToggled}
		<div
			transition:fade|local={{ duration: fadeDuration }}
			class="bar"
			id="bar2"
			style={'width: 32px'}
		/>
	{/if}
	<div
		class="bar"
		id="bar3"
		style="width: {$xBarWidth}px; transform: rotate({$bottomBarRotation}deg)"
	/>
</div>

<style>
	#menu-wrapper {
		box-sizing: content-box;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: flex-end;
		width: 32px;
		height: 24px;
		padding: 12px 8px 12px 8px;
		cursor: pointer;
	}
	.bar {
		height: 4px;
		background-color: black;
		transform-origin: right center;
	}
</style>
