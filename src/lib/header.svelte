<script>
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
</script>

<Navbar
	let:hidden
	let:toggle
	rounded
	color="none"
	class="fixed left-0 top-0 z-20 bg-background-light text-font-white"
>
	<NavBrand href="/">
		<span class="self-center whitespace-nowrap py-8 text-3xl font-semibold text-font-white">
			Habitat Hive
		</span>
	</NavBrand>
	<NavHamburger on:click={toggle} />
	<NavUl {hidden} class="text-font-white">
		<a href="/hive-finder"
			><button
				class="rounded-lg bg-primary p-2 font-semibold text-font-white hover:bg-background-light"
				>Find Rental</button
			></a
		>
	</NavUl>
</Navbar>
