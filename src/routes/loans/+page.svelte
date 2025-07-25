<script lang="ts">
	import * as Card from '$lib/components/ui/card/index.js';
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
    <h1 class="text-3xl">Loan</h1>
    <div class="flex flex-col md:grid md:grid-cols-3 gap-2">
        <div class="md:col-span-3">
            <div class="flex flex-col md:flex-row gap-2">
                <Card.Root class="flex flex-col justify-center flex-1">
                    <Card.Header>
                        <Card.Title class="text-2xl">
                            Total Loan
                        </Card.Title>
                    </Card.Header>
                    <Card.Content>
                        <p>MYR 20,000.00</p>
                    </Card.Content>
                </Card.Root>
                <Card.Root class="flex flex-col justify-center flex-1">
                    <Card.Header>
                        <Card.Title class="text-2xl">
                            Total Repayment Remaining
                        </Card.Title>
                    </Card.Header>
                    <Card.Content>
                        <p>36 Months</p>
                    </Card.Content>
                </Card.Root>
                <Card.Root class="flex flex-col justify-center flex-1">
                    <Card.Header>
                        <Card.Title class="text-2xl">
                            Overdue Amount
                        </Card.Title>
                    </Card.Header>
                    <Card.Content>
                        <p>MYR 00.00</p>
                    </Card.Content>
                </Card.Root>
            </div>
        </div>
        <Card.Root class="flex flex-col md:col-span-3">
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
        </Card.Root>
        <Card.Root>
			<Card.Header>
				<Card.Title>Personal Loan</Card.Title>
				<Card.Description>MYR 1,200.00</Card.Description>
			</Card.Header>
		</Card.Root>
        <Card.Root>
			<Card.Header>
				<Card.Title>House Loan</Card.Title>
				<Card.Description>MYR 122,000.00</Card.Description>
			</Card.Header>
		</Card.Root>
        <Card.Root>
			<Card.Header>
				<Card.Title>Car Loan</Card.Title>
				<Card.Description>MYR 24,000.00</Card.Description>
			</Card.Header>
		</Card.Root>
    </div>
</div>

<!--Add pay button to each loan card-->