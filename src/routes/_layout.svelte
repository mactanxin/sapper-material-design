<script>
	import Nav from '../components/Nav.svelte';
	import Footer from '../components/Footer.svelte';
	export let segment;
</script>

<style>
	main {
		position: relative;
		max-width: 960px;
		background-color: white;
		padding: 60px 10px;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>

<Nav {segment}/>
<main>
	<slot></slot>
</main>

<Footer />