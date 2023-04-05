<script>
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger, Button } from 'flowbite-svelte';
</script>

<Navbar
	let:hidden
	let:toggle
	fixed
	rounded
	color="none"
	class="bg-background-light text-font-white"
>
	<NavBrand href="/">
		<span class="self-center whitespace-nowrap py-8 text-3xl font-semibold text-font-white">
			Habitat Hive
		</span>
	</NavBrand>
	<NavHamburger on:click={toggle} />
	<NavUl {hidden} class="text-font-white">
		<Button class="rounded-lg bg-primary font-semibold text-font-white">Find Rental</Button>
	</NavUl>
</Navbar>
