<script lang="ts">
	import '../app.css';
	import * as NavigationMenu from '$lib/components/ui/navigation-menu/index.js';
	import * as Drawer from '$lib/components/ui/drawer/index.js';
	import { navigationMenuTriggerStyle } from '$lib/components/ui/navigation-menu/navigation-menu-trigger.svelte';
	import { onNavigate } from '$app/navigation';
	import { MediaQuery } from 'svelte/reactivity';
	import DrawerClose from '$lib/components/ui/drawer/drawer-close.svelte';
	import { Menu } from '@lucide/svelte';

	onNavigate((navigation) => {
		if (!document.startViewTransition) return;

		return new Promise((resolve) => {
			document.startViewTransition(async () => {
				resolve();
				await navigation.complete;
			});
		});
	});

	const isDesktop = new MediaQuery('(min-width: 768px)');

	let { children } = $props();
</script>

{#if isDesktop.current}
	<div class="mx-5 mt-5 flex gap-45 items-center justify-center">
		<!--Add fake bank logo here-->
		<p>MyBank</p>
		<NavigationMenu.Root>
			<NavigationMenu.List class="flex gap-20">
				<NavigationMenu.Item>
					<NavigationMenu.Link>
						{#snippet child()}
							<a href="./" class={navigationMenuTriggerStyle()}>My Accounts</a>
						{/snippet}
					</NavigationMenu.Link>
				</NavigationMenu.Item>
				<NavigationMenu.Item>
					<NavigationMenu.Link>
						{#snippet child()}
							<a href="cards" class={navigationMenuTriggerStyle()}>Cards</a>
						{/snippet}
					</NavigationMenu.Link>
				</NavigationMenu.Item>
				<NavigationMenu.Item>
					<NavigationMenu.Link>
						{#snippet child()}
							<a href="loans" class={navigationMenuTriggerStyle()}>Loans/Financing</a>
						{/snippet}
					</NavigationMenu.Link>
				</NavigationMenu.Item>
				<NavigationMenu.Item>
					<NavigationMenu.Link>
						{#snippet child()}
							<a href="wealth" class={navigationMenuTriggerStyle()}>Wealth</a>
						{/snippet}
					</NavigationMenu.Link>
				</NavigationMenu.Item>
			</NavigationMenu.List>
		</NavigationMenu.Root>
	</div>
{:else}
	<div class="ml-5 pt-5">
		<Drawer.Root direction="top">
			<!--Replace with three-line menu symbol-->
			<Drawer.Trigger>
				<span class="sr-only">Menu</span>
				<Menu />
			</Drawer.Trigger>
			<Drawer.Content class="py-5 flex flex-col items-start justify-center gap-10">
				<Drawer.Close>
					<a href="./" class={navigationMenuTriggerStyle()}>My Accounts</a>
				</Drawer.Close>
				<DrawerClose>
					<a href="cards" class={navigationMenuTriggerStyle()}>Cards</a>
				</DrawerClose>
				<Drawer.Close>
					<a href="loans" class={navigationMenuTriggerStyle()}>Loan/Financing</a>
				</Drawer.Close>
				<Drawer.Close>
					<a href="wealth" class={navigationMenuTriggerStyle()}>Wealth</a>
				</Drawer.Close>
			</Drawer.Content>
		</Drawer.Root>
	</div>
{/if}

<main class="p-16 min-h-[87dvh]">
	{@render children()}
</main>


<footer class="flex flex-col items-center justify-center p-5">
	<p>© 2025 MyBank Sdn Bhd. All Rights Reserved.</p>
</footer>
