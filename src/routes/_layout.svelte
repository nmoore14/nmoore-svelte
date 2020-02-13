<script>
	import Nav from '../components/Nav.svelte';
	import Background from '../components/Background.svelte';

	export let segment;
</script>

<style>

</style>

<main class="flex flex-col w-full h-full">
	<Nav {segment}/>
	<slot></slot>
	<Background />
</main>