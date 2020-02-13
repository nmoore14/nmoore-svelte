<script>
	import { x_value, y_value, x_css, y_css } from '../store.js';

  function handleMousemove(event) {
		let newX = Math.floor((event.clientX / 1920) * 10) + 2;
		let newY = Math.floor((event.clientY / 1920) * 10) + 2;
		x_value.update(x => event.clientX);
		y_value.update(y => event.clientY);
		x_css.update(n => newX);
		y_css.update(k => newY);
	}
</script>

<svelte:head>
	<title>Nick Moore | Developer</title>
</svelte:head>

<div class="z-1 flex flex-row w-screen h-screen bg-transparent-0" on:mousemove={handleMousemove}>
	<h1 class="w-full font-sans font-thin text-center p-4 bg-transparent-0">Nick Moore</h1>
</div>