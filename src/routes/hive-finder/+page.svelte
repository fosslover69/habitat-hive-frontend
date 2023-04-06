<script>
	// @ts-nocheck
	import {
		NumberInput,
		Label,
		Helper,
		Select,
		Table,
		TableBody,
		TableBodyCell,
		TableBodyRow,
		TableHead,
		TableHeadCell
	} from 'flowbite-svelte';
	let areacode = 812;
	let hiveType = [
		{
			name: 'Apartment',
			value: 'Apartment'
		},
		{
			name: 'Duplex',
			value: 'Duplex'
		},
		{
			name: 'Single Family Home',
			value: 'Single-family home'
		},
		{
			name: 'Bungalow',
			value: 'Bungalow'
		}
	];
	let hiveFurnish = [
		{
			name: 'Semi Furnished',
			value: 'Semi_Furnished'
		},
		{
			name: 'Fully Furnished',
			value: 'Fully Furnished'
		},
		{
			name: 'Unfurnished',
			value: 'Unfurnished'
		}
	];
	let selectedHiveType;
	let selectedHiveFurnish;
	import Papa from 'papaparse';
	import { onMount } from 'svelte';

	let data = [];
	let filteredData = [];
	onMount(async () => {
		const file = await fetch('./Final_df.csv').then((res) => res.text());
		Papa.parse(file, {
			header: true,
			dynamicTyping: true,
			complete: (results) => {
				data = results.data;
				console.log(data.filter((d) => d.Property_Area === areacode));
			}
		});
	});
	function findHive() {
		filteredData = data
			.filter(
				(d) =>
					d.Property_Area === areacode &&
					(selectedHiveType ? d.Property_Type === selectedHiveType : true) &&
					(selectedHiveFurnish ? d.Furnishing === selectedHiveFurnish : true)
			)
			.sort((a, b) => b.Habitability_score - a.Habitability_score);
	}
</script>

<div class="my-8">
	<h1 class="text-center text-4xl font-bold text-primary">Hive Finder</h1>
	<div class="my-8">
		<form>
			<div class="flex w-screen flex-wrap items-end justify-center gap-8">
				<div class=" text-font-white">
					<Label class="block space-y-2">
						<span class="text-xl text-font-white">Area Code</span>
					</Label>
					<NumberInput
						label="Area Code"
						id="areacode"
						name="areacode"
						required
						placeholder="Enter your area code"
						bind:value={areacode}
					/>
				</div>
				<div>
					<Label>
						<span class="text-xl text-font-white">Hive Type</span></Label
					>
					<Select items={hiveType} bind:value={selectedHiveType} />
				</div>
				<div>
					<Label>
						<span class="text-xl text-font-white">Furnishing Type</span>
					</Label>
					<Select items={hiveFurnish} bind:value={selectedHiveFurnish} />
				</div>
				<div>
					<button
						class="rounded-lg bg-primary p-2 text-font-white hover:bg-background-light"
						on:click={() => findHive()}>Submit</button
					>
				</div>
			</div>
		</form>
	</div>
	<div class="flex items-center justify-center">
		<div class="rounded-lg">
			<TableHead class="rounded-xl bg-primary">
				<TableHeadCell>Property ID</TableHeadCell>
				<TableHeadCell class="border-l-2 border-font-white">Property Type</TableHeadCell>
				<TableHeadCell class="border-l-2 border-font-white">Furnishing</TableHeadCell>
				<TableHeadCell class="border-l-2 border-font-white">Habitability Score</TableHeadCell>
				<TableHeadCell class="border-l-2 border-font-white">Neighborhood Review</TableHeadCell>
			</TableHead>

			<TableBody class="divide-y text-center">
				{#if filteredData.length === 0}
					<TableBodyRow class="bg-background-light text-center">
						<TableBodyCell colspan="5">No Data</TableBodyCell>
					</TableBodyRow>
				{/if}
				{#each filteredData as item}
					<TableBodyRow class="bg-background-light">
						<TableBodyCell class="border-b-2  border-font-white">{item.Property_ID}</TableBodyCell>
						<TableBodyCell class="border-b-2 border-l-2 border-font-white"
							>{item.Property_Type}</TableBodyCell
						>
						<TableBodyCell class="border-b-2 border-l-2 border-font-white"
							>{item.Furnishing}</TableBodyCell
						>
						<TableBodyCell class="border-b-2 border-l-2 border-font-white"
							>{item.Habitability_score}</TableBodyCell
						>
						<TableBodyCell class="border-b-2 border-l-2 border-font-white"
							>{item.Neighborhood_Review}</TableBodyCell
						>
					</TableBodyRow>
				{/each}
			</TableBody>
		</div>
	</div>
</div>
