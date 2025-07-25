<script>
	import DarkModeToggleButton from "$lib/components/dark-mode-toggle-button.svelte";
</script>

<div class="flex flex-col gap-10 place-items-center">
	<h1 class="text-3xl self-start">Settings</h1>
    <div class="grid grid-cols-2 w-[70%] place-items-center">
        <p>Enable Dark Mode</p>
        <DarkModeToggleButton />
    </div>
</div>

<!--Change to dropdown with three options-->