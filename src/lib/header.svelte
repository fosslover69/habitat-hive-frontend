<script>
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
</script>

<Navbar
	rounded
	color="none"
	class="fixed left-0 top-0 z-20 w-screen bg-background-light px-8 text-font-white"
>
	<NavBrand href="/">
		<span
			class="self-center whitespace-nowrap py-4 text-2xl font-semibold text-font-white sm:text-3xl lg:py-8"
		>
			Habitat Hive
		</span>
	</NavBrand>
	<a href="/hive-finder"
		><button
			class="rounded-lg bg-primary p-2 text-xs font-semibold text-font-white hover:bg-background-light lg:text-lg"
			>Find Rental</button
		></a
	>
</Navbar>
