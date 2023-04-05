<script>
	import '../app.postcss';
	import Footer from '../lib/footer.svelte';
	import Header from '../lib/header.svelte';
</script>

<div class="bg-background">
	<Header />
	<slot />
	<Footer />
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Gilda+Display&display=swap');
	:root {
		font-family: 'Gilda Display', serif;
		background-color: #13100c;
	}
	.btnClass:hover {
		background-color: #1f1a14;
		color: #1f1a14;
	}
</style>
