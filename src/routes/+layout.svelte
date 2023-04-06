<script>
	import '../app.postcss';
	import Footer from '../lib/footer.svelte';
	import Header from '../lib/header.svelte';
</script>

<div class="bg-background">
	<Header />
	<div class="py-32 lg:pb-8 lg:pt-44">
		<slot />
	</div>
	<Footer />
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Gilda+Display&display=swap');
	:root {
		font-family: 'Gilda Display', serif;
		background-color: #13100c;
		scroll-behavior: smooth;
	}
</style>
