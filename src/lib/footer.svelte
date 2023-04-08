<script>
	import { FooterLink, FooterLinkGroup } from 'flowbite-svelte';
</script>

<div
	class="fixed bottom-0 left-0 flex w-screen items-center justify-between bg-background-light px-8 py-4 text-font-white lg:px-48"
>
	<div class="text-2xl">Habitat Hive</div>
	<FooterLinkGroup
		ulClass="flex flex-wrap items-center mt-3 text-sm text-gray-500 dark:text-gray-400 sm:mt-0"
	>
		<FooterLink href="/">
			<img
				src="https://ik.imagekit.io/corvus/twitter.svg?updatedAt=1680707927020"
				alt="Twitter"
				class="w-6 lg:w-12"
			/>
		</FooterLink>
		<FooterLink href="/">
			<img
				src="https://ik.imagekit.io/corvus/instagram.svg?updatedAt=1680707927020"
				alt="Instagram"
				class="w-6 lg:w-12"
			/>
		</FooterLink>
		<FooterLink href="/">
			<img
				src="https://ik.imagekit.io/corvus/facebook.svg?updatedAt=1680707927020"
				alt="Facebook"
				class="w-6 lg:w-12"
			/>
		</FooterLink>
	</FooterLinkGroup>
</div>
