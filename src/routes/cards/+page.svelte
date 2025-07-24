<script lang="ts">
	import EllipsisIcon from '@lucide/svelte/icons/ellipsis';
	import * as Card from '$lib/components/ui/card/index.js';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu/index.js';
	import { Button } from '$lib/components/ui/button/index.js';

	import TrendingUpIcon from '@lucide/svelte/icons/trending-up';
	import * as Chart from '$lib/components/ui/chart/index.js';
	import { PieChart } from 'layerchart';

	const chartData = [
		{ browser: 'chrome', visitors: 275, color: 'var(--color-chrome)' },
		{ browser: 'safari', visitors: 200, color: 'var(--color-safari)' },
		{ browser: 'firefox', visitors: 287, color: 'var(--color-firefox)' },
		{ browser: 'edge', visitors: 173, color: 'var(--color-edge)' },
		{ browser: 'other', visitors: 190, color: 'var(--color-other)' }
	];
	const chartConfig = {
		visitors: { label: 'Visitors' },
		chrome: { label: 'Chrome', color: 'var(--chart-1)' },
		safari: { label: 'Safari', color: 'var(--chart-2)' },
		firefox: { label: 'Firefox', color: 'var(--chart-3)' },
		edge: { label: 'Edge', color: 'var(--chart-4)' },
		other: { label: 'Other', color: 'var(--chart-5)' }
	} satisfies Chart.ChartConfig;
</script>

<div class="flex flex-col gap-10">
	<h1 class="text-3xl">Cards</h1>
	<div class="flex flex-col gap-4 md:grid md:grid-cols-2">
		<Card.Root>
			<Card.Header>
				<Card.Title>Card 1</Card.Title>
				<Card.Description>xxxx-xxxx-xxxx-xxxx</Card.Description>
				<Card.Action>
					<DropdownMenu.Root>
						<DropdownMenu.Trigger>
							{#snippet child({ props })}
								<Button {...props} variant="link" size="icon" class="relative size-8 p-0">
									<span class="sr-only">Open Menu</span>
									<EllipsisIcon />
								</Button>
							{/snippet}
						</DropdownMenu.Trigger>
						<DropdownMenu.Content>
							<DropdownMenu.Item>Add/Remove Spending Reminder</DropdownMenu.Item>
							<DropdownMenu.Item>Update Purchase Limit</DropdownMenu.Item>
							<DropdownMenu.Item>Overseas Activation</DropdownMenu.Item>
							<DropdownMenu.Item>Manage My Debit Card</DropdownMenu.Item>
						</DropdownMenu.Content>
					</DropdownMenu.Root>
				</Card.Action>
			</Card.Header>
			<Card.Content>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img src="#" />
			</Card.Content>
		</Card.Root>
		<Card.Root>
			<Card.Header>
				<Card.Title>Card 2</Card.Title>
				<Card.Description>xxxx-xxxx-xxxx-xxxx</Card.Description>
				<Card.Action>
					<DropdownMenu.Root>
						<DropdownMenu.Trigger>
							{#snippet child({ props })}
								<Button {...props} variant="link" size="icon" class="relative size-8 p-0">
									<span class="sr-only">Open Menu</span>
									<EllipsisIcon />
								</Button>
							{/snippet}
						</DropdownMenu.Trigger>
						<DropdownMenu.Content>
							<DropdownMenu.Item>Add/Remove Spending Reminder</DropdownMenu.Item>
							<DropdownMenu.Item>Update Purchase Limit</DropdownMenu.Item>
							<DropdownMenu.Item>Overseas Activation</DropdownMenu.Item>
							<DropdownMenu.Item>Manage My Debit Card</DropdownMenu.Item>
						</DropdownMenu.Content>
					</DropdownMenu.Root>
				</Card.Action>
			</Card.Header>
			<Card.Content>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img src="#" />
			</Card.Content>
		</Card.Root>
	</div>
    <div class="flex flex-col gap-2">
        <div class="flex justify-center items-center m-2">
            <h2 class="font-bold">Total Expenditure</h2>
        </div>
        <div class="flex flex-col md:grid md:grid-cols-2 gap-2">
            <Card.Root class="flex flex-col">
                <Card.Header class="items-center">
                    <Card.Title>Pie Chart - Donut</Card.Title>
                    <Card.Description>January - June 2024</Card.Description>
                </Card.Header>
                <Card.Content class="flex-1">
                    <Chart.Container config={chartConfig} class="mx-auto aspect-square max-h-[250px]">
                        <PieChart
                            data={chartData}
                            key="browser"
                            value="visitors"
                            c="color"
                            innerRadius={60}
                            padding={29}
                            props={{ pie: { motion: 'tween' } }}
                        >
                            {#snippet tooltip()}
                                <Chart.Tooltip hideLabel />
                            {/snippet}
                        </PieChart>
                    </Chart.Container>
                </Card.Content>
                <Card.Footer class="flex-col gap-2 text-sm">
                    <div class="flex items-center gap-2 leading-none font-medium">
                        Trending up by 5.2% this month <TrendingUpIcon class="size-4" />
                    </div>
                    <div class="leading-none text-muted-foreground">
                        Showing total visitors for the last 6 months
                    </div>
                </Card.Footer>
            </Card.Root>
            <div>
                <p>Combobox showing all cards own</p>
                <p>Data Table</p>
            </div>
        </div>
    </div>
</div>
