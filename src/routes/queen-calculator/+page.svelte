<script>
	import { Input } from 'flowbite-svelte';
</script>

<h1 class="mb-8 text-center text-4xl font-bold text-primary">Queen Comfort Calculator</h1>
<form class="px-8">
	<div class="mb-6 grid gap-6 text-font-white md:grid-cols-2">
		<div>
			<span>Property Area</span>
			<Input class="mt-2" type="number" id="first_name" placeholder="820" required />
		</div>
		<div>
			<span>Property Type</span>
			<Input class="mt-2" type="text" id="last_name" placeholder="Duplex" required />
		</div>
		<div>
			<span>Furnishing</span>
			<Input class="mt-2" type="text" id="company" placeholder="Fully Furnished" required />
		</div>
		<div>
			<span>Number of Windows</span>
			<Input class="mt-2" type="number" id="phone" placeholder="6" required />
		</div>
		<div>
			<span>Number of Doors</span>
			<Input class="mt-2" type="number" id="website" placeholder="2" required />
		</div>
	</div>
	<button class="rounded-lg bg-primary p-2 text-font-white hover:bg-background-light" type="submit"
		>Submit</button
	>
</form>
