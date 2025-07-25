<script lang="ts">
	import * as Card from '$lib/components/ui/card/index.js';
</script>

<div class="flex flex-col gap-10">
	<h1 class="text-3xl">Wealth</h1>
	<div class="grid grid-cols-1 items-center justify-center gap-2 md:grid md:grid-cols-2">
		<Card.Root>
			<Card.Header>
				<Card.Title class="text-2xl">Total Assets</Card.Title>
				<Card.Description>MYR 24,000.00</Card.Description>
			</Card.Header>
		</Card.Root>
		<Card.Root>
			<Card.Header>
				<Card.Title class="text-2xl">Total Liabilities</Card.Title>
				<Card.Description>MYR 24,000.00</Card.Description>
			</Card.Header>
		</Card.Root>
	</div>
    <!--Sorting data table through combobox-->
	<p>Combobox</p>
	<p>Breakdown on Assets</p>
	<p>Breakdown on Liabilities</p>
</div>
