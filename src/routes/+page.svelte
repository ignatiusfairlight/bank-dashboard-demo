<script lang="ts">
    import EllipsisIcon from "@lucide/svelte/icons/ellipsis";
    import * as Card from "$lib/components/ui/card/index.js";
    import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
    import { Button } from "$lib/components/ui/button/index.js";
</script>

<div class="flex flex-col gap-10">
    <h1 class="text-3xl">My Accounts</h1>
    <div class="flex flex-col gap-5">
        <Card.Root>
            <Card.Header class="flex flex-col justify-center items-center">
                <Card.Title class="text-3xl md:text-4xl">
                    RM 44,500.00
                </Card.Title>
                <Card.Description>
                    Total Balance
                </Card.Description>
            </Card.Header>
        </Card.Root>
        <Card.Root class="bg-red-400">
            <Card.Header>
                <Card.Title class="text-2xl">
                    Savings Account-Alpha
                </Card.Title>
                <Card.Description>
                    7483 9162 5084
                </Card.Description>
                <Card.Action>
                    <DropdownMenu.Root>
                        <DropdownMenu.Trigger>
                            {#snippet child({ props })}
                                <Button
                                    {...props}
                                    variant="link"
                                    size="icon"
                                    class="relative size-8 p-0"
                                >
                                    <span class="sr-only">Open Menu</span>
                                    <EllipsisIcon />
                                </Button>
                            {/snippet}
                        </DropdownMenu.Trigger>
                        <DropdownMenu.Content>
                            <DropdownMenu.Item>View Details</DropdownMenu.Item>
                            <DropdownMenu.Item>Transfer Funds</DropdownMenu.Item>
                            <DropdownMenu.Item>View Statements</DropdownMenu.Item>
                            <DropdownMenu.Item>Edit Account Name</DropdownMenu.Item>
                        </DropdownMenu.Content>
                    </DropdownMenu.Root>
                </Card.Action>
            </Card.Header>
            <Card.Content>
                <p>RM20,000.00</p>
            </Card.Content>
        </Card.Root>
        <Card.Root class="bg-amber-400">
            <Card.Header>
                <Card.Title class="text-2xl">
                    Current Account-i
                </Card.Title>
                <Card.Description>
                    7483 9162 5084
                </Card.Description>
                <Card.Action>
                    <DropdownMenu.Root>
                        <DropdownMenu.Trigger>
                            {#snippet child({ props })}
                                <Button
                                    {...props}
                                    variant="link"
                                    size="icon"
                                    class="relative size-8 p-0"
                                >
                                    <span class="sr-only">Open Menu</span>
                                    <EllipsisIcon />
                                </Button>
                            {/snippet}
                        </DropdownMenu.Trigger>
                        <DropdownMenu.Content>
                            <DropdownMenu.Item>View Details</DropdownMenu.Item>
                            <DropdownMenu.Item>Transfer Funds</DropdownMenu.Item>
                            <DropdownMenu.Item>View Statements</DropdownMenu.Item>
                            <DropdownMenu.Item>Edit Account Name</DropdownMenu.Item>
                        </DropdownMenu.Content>
                    </DropdownMenu.Root>
                </Card.Action>
            </Card.Header>
            <Card.Content>
                <p>RM24,500.00</p>
            </Card.Content>
        </Card.Root>
    </div>
    <div class="flex flex-col gap-4 md:grid md:grid-cols-3">
        <Card.Root class="shadow-sm hover:shadow-xl hover:bg-gray-50 hover:text-black transition-all duration-300 ease-in-out rounded-xl">
            <Card.Header class="flex justify-center">
                <Card.Title>Open New Account</Card.Title>
            </Card.Header>
        </Card.Root>
        <Card.Root class="shadow-sm hover:shadow-xl hover:bg-gray-50 hover:text-black transition-all duration-300 ease-in-out rounded-xl">
            <Card.Header class="flex justify-center">
                <Card.Title>Pay Bills</Card.Title>
            </Card.Header>
        </Card.Root>
        <Card.Root class="shadow-sm hover:shadow-xl hover:bg-gray-50 hover:text-black transition-all duration-300 ease-in-out rounded-xl">
            <Card.Header class="flex justify-center">
                <Card.Title>Link Overseas Account</Card.Title>
            </Card.Header>
        </Card.Root>
    </div>
</div>


