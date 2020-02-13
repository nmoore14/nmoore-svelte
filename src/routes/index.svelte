<script>
	import { x_value, y_value, x_css, y_css } from '../store.js';

  function handleMousemove(event) {
		x_value.update(x => event.clientX);
		y_value.update(y => event.clientY);
		x_css.update(n => getPoint(event.clientX));
		y_css.update(k => getPoint(event.clientY));
	}

	function getPoint(pos) {
		return (pos / 1920) + 2;
	}
</script>

<svelte:head>
	<title>Nick Moore | Developer</title>
</svelte:head>

<div class="z-1 flex flex-row w-screen h-screen" on:mousemove={handleMousemove}>
	<h1 class="w-full font-sans font-thin text-center p-4">Nick Moore</h1>
</div>