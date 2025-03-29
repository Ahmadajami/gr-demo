<script lang="ts">
	import { Zap, Bird, Menu } from '@lucide/svelte';
	import * as Sheet from '$lib/components/ui/sheet/index';
	import Button from '../ui/button/button.svelte';

	let open = $state(false);
</script>

<div class="w-full" id="top">
	<div id="top" class="border-b bg-black text-white">
		<div class="flex h-16 items-center justify-between px-4">
			<!-- Logo and Project Name -->
			<a class="flex w-1/3 items-center gap-2 md:w-fit" href="/">
				<div class="rounded-lg border p-2 2xl:hidden">
					<Bird class="h-5 w-5" />
				</div>
				<div class="hidden 2xl:block">
					<Zap class="h-5 w-5" />
				</div>
				<h2 class="hidden text-center text-sm font-semibold lg:flex">{PUBLIC_APP_NAME}</h2>
			</a>

			<a href="/">
				<h2 class="text-center text-sm font-semibold lg:hidden">{Grresin}</h2>
			</a>

			<!-- Desktop Navigation -->
			<div class="mx-4 hidden w-1/3 flex-1 items-start justify-start lg:flex">
				<nav class="flex gap-6">
					<Button variant="ghost" size="sm" href="/">Home</Button>
					<Button variant="ghost" size="sm" href="/">Blog</Button>
					<Button variant="ghost" size="sm" href="#top">AboutUs</Button>
					<Button variant="ghost" size="sm" href="/">Order a Floor</Button>
				</nav>
			</div>

			<div class="flex w-1/3 items-center justify-end gap-4">
				<Button variant="ghost" size="sm" class="hidden lg:flex">Contact Us</Button>

				<!-- Mobile Menu Button -->
				<Button variant="ghost" size="icon" class="lg:hidden" onclick={() => (open = true)}>
					<Menu class="h-5 w-5" />
				</Button>
			</div>
		</div>
	</div>

	<!-- Mobile Sheet/Drawer -->
	<Sheet.Root bind:open>
		<Sheet.Content side="left" class="w-64 bg-popover">
			<div class="">
				<div class="mb-6 flex items-center justify-start gap-x-3">
					<div class="rounded-lg border p-2">
						<Bird class="h-5 w-5" />
					</div>
					<span class="text-md font-semibold">Menu</span>
				</div>
				<nav class="flex flex-col space-y-1">
					<Button variant="ghost" class="justify-start" href="/" onclick={() => (open = false)}
						>Sign In</Button
					>
					<Button variant="ghost" class="justify-start" href="/" onclick={() => (open = false)}
						>Account</Button
					>
					<Button variant="ghost" class="justify-start" href="#top" onclick={() => (open = false)}
						>Contact</Button
					>
					<Button variant="ghost" class="justify-start" href="#top" onclick={() => (open = false)}
						>Privacy</Button
					>
				</nav>
			</div>
		</Sheet.Content>
	</Sheet.Root>
</div>
