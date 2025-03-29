<script lang="ts">
	import '../app.css';
	import Navbar from '$lib/components/layout/Navbar.svelte';
	import Footer from '$lib/components/layout/Footer.svelte';
	import { page } from '$app/state';
	import { locales, localizeHref } from '$lib/paraglide/runtime';

	let { children } = $props();
</script>

<div style="display:none">
	{#each locales as locale}
		<a href={localizeHref(page.url.pathname, { locale })}>{locale}</a>
	{/each}
</div>
<Navbar />
<main class="min-h-screen bg-[url('topography.svg')] bg-cover bg-center">
	{@render children()}
</main>
<Footer />
