<script lang="ts">
    import * as Card from "$lib/components/ui/card/index.js";
</script>

<div class="flex flex-col gap-10">
    <h1 class="text-3xl">My Accounts</h1>
    <div class="flex flex-col gap-5">
        <Card.Root>
            <Card.Header class="flex flex-col justify-center items-center">
                <Card.Title>
                    <h2 class="text-3xl md:text-4xl">RM 44,500.00</h2>
                </Card.Title>
                <Card.Description>
                    <h3>Total Balance</h3>
                </Card.Description>
            </Card.Header>
        </Card.Root>
        <Card.Root class="bg-red-400">
            <Card.Header class="flex flex-col justify-center items-start">
                <Card.Title>
                    <h2 class="text-2xl">Savings Account-Alpha</h2>
                </Card.Title>
                <Card.Description>
                    <h3>7483 9162 5084</h3>
                </Card.Description>
            </Card.Header>
            <Card.Content>
                <p>RM20,000.00</p>
            </Card.Content>
        </Card.Root>
        <Card.Root class="bg-amber-400">
            <Card.Header class="flex flex-col justify-center items-start">
                <Card.Title>
                    <h2 class="text-2xl">Current Account-i</h2>
                </Card.Title>
                <Card.Description>
                    <h3>7483 9162 5084</h3>
                </Card.Description>
            </Card.Header>
            <Card.Content>
                <p>RM24,500.00</p>
            </Card.Content>
        </Card.Root>
    </div>
</div>


