<script>
	import { FooterLink, FooterLinkGroup } from 'flowbite-svelte';
</script>

<div
	class="fixed bottom-0 left-0 z-20 flex w-full items-center justify-between bg-background-light px-48 py-8 text-font-white"
>
	<div class="text-2xl">Habitat Hive</div>
	<FooterLinkGroup
		ulClass="flex flex-wrap items-center mt-3 text-sm text-gray-500 dark:text-gray-400 sm:mt-0"
	>
		<FooterLink href="/">
			<img
				src="https://ik.imagekit.io/corvus/twitter.svg?updatedAt=1680707927020"
				alt="Twitter"
				width="40px"
			/>
		</FooterLink>
		<FooterLink href="/">
			<img
				src="https://ik.imagekit.io/corvus/instagram.svg?updatedAt=1680707927020"
				alt="Instagram"
				width="40px"
			/>
		</FooterLink>
		<FooterLink href="/">
			<img
				src="https://ik.imagekit.io/corvus/facebook.svg?updatedAt=1680707927020"
				alt="Facebook"
				width="40px"
			/>
		</FooterLink>
	</FooterLinkGroup>
</div>
