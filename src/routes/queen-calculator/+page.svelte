<script>
	// @ts-nocheck

	import { Input, Progressbar, Modal } from 'flowbite-svelte';
	let areacode, type, furnishing, windows, doors;
	let value = 0;
	let modal = false;
	async function postReq() {
		const response = await fetch('http://localhost:5000/process-data', {
			method: 'POST',
			headers: {
				'Content-Type': 'application/json'
			},
			body: JSON.stringify({
				areacode,
				type,
				furnishing,
				windows,
				doors
			})
		});
		const data = await response.json();
		value = data.habitability;
		value = value.toFixed(2);
		modal = true;
		console.log(value);
	}
</script>

<h1 class="mb-8 text-center text-4xl font-bold text-primary">Queen Comfort Calculator</h1>
<form class="flex items-center justify-center px-8">
	<div class="w-full lg:w-1/2">
		<div class="mb-6 grid gap-6 text-font-white md:grid-cols-2">
			<div>
				<span>Property Area</span>
				<Input
					class="mt-2"
					type="number"
					id="first_name"
					bind:value={areacode}
					placeholder="820"
					required
				/>
			</div>
			<div>
				<span>Property Type</span>
				<Input
					class="mt-2"
					type="text"
					id="last_name"
					bind:value={type}
					placeholder="Duplex"
					required
				/>
			</div>
			<div>
				<span>Furnishing</span>
				<Input
					class="mt-2"
					type="text"
					id="company"
					bind:value={furnishing}
					placeholder="Fully Furnished"
					required
				/>
			</div>
			<div>
				<span>Number of Windows</span>
				<Input
					class="mt-2"
					type="number"
					id="phone"
					bind:value={windows}
					placeholder="6"
					required
				/>
			</div>
			<div>
				<span>Number of Doors</span>
				<Input
					class="mt-2"
					type="number"
					id="website"
					bind:value={doors}
					placeholder="2"
					required
				/>
			</div>
		</div>
		<button
			class="rounded-lg bg-primary p-2 text-font-white hover:bg-background-light"
			type="submit"
			on:click={() => postReq()}>Submit</button
		>
		<Modal title="Habitability Score" class="bg-background-light" bind:open={modal} autoclose>
			<Progressbar progress={value} size="h-10" color="yellow" class="my-4" />
			Your habitability Score: {value}
			<svelte:fragment slot="footer">
				<button>Close</button>
			</svelte:fragment>
		</Modal>
	</div>
</form>
