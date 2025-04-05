<script lang="ts">
	import { ChartBar, Lightbulb, TrendingUp, ChevronRight } from '@lucide/svelte';

	import Carousel from '$lib/components/Carousel.svelte';
	import BlureFade from '$lib/BlureFade.svelte';
	import Hr from '$lib/components/HR.svelte';
	import BentoGrid from '$lib/components/layout/Grid/BentoGrid.svelte';
	import { m } from '$lib/paraglide/messages';

	const services = [
		{
			title: 'Strategic Planning',
			description: 'Custom strategies tailored to your business goals and market position.',
			icon: ChartBar
		},
		{
			title: 'Innovation Consulting',
			description: 'Transform your ideas into actionable business solutions.',
			icon: Lightbulb
		},
		{
			title: 'Growth Solutions',
			description: 'Scale your business with data-driven growth strategies.',
			icon: TrendingUp
		}
	];
</script>

<section class="relative overflow-hidden px-4 py-3 sm:px-6 lg:px-8">
	<div class="container mx-auto">
		<div class="grid items-center gap-12 md:grid-cols-2 md:gap-16">
			<div
				class="order-2 flex h-full flex-col items-center text-center md:order-1 md:items-start md:text-left"
			>
				<div class="flex h-full w-full flex-col">
					<div class="w-full">
						<img class="mb-0 max-h-[350px] max-w-full" src="Logo.png" alt="Graffiti Resin Logo" />
					</div>
					<div class=" p-2">
						<BlureFade>
							<h1
								class="myshadow ml-2 text-4xl font-bold tracking-tight sm:text-5xl lg:text-6xl rtl:text-start"
							>
								{m.welcome()}<br />
								{m.welcomeHeader()}
							</h1>
						</BlureFade>
					</div>
				</div>
			</div>

			<div class="order-1 md:order-2">
				<div class="relative z-10 max-w-full">
					<Carousel />
				</div>
			</div>
		</div>
	</div>

	<p
		style="white-space: pre-line"
		class="ltr:ml-18 container mx-auto mt-6 text-lg leading-relaxed text-muted-foreground sm:mr-0 ltr:w-full rtl:mr-0 rtl:w-full md:rtl:mr-11"
	>
		{m.welcomeDesc()}
	</p>
</section>

<section class="mt-12 flex flex-col px-4 py-20 lg:px-8">
	<BlureFade delay={0.2}>
		<h1 class="  myshadow ml-11 w-fit text-4xl font-bold tracking-tight sm:text-5xl lg:text-6xl">
			{m.department()}<br />
		</h1>
	</BlureFade>

	<article class=" mt-8 h-96">
		<BentoGrid />
	</article>
</section>

<section class=" bg-[#a71580] py-20 text-white">
	<div class="container mx-auto px-4">
		<h1 class="text-2xl font-semibold tracking-tight sm:text-3xl lg:text-4xl">
			What services do we offer at
		</h1>
		<br />
		<h2 class=" w-fit text-2xl font-semibold tracking-tight sm:text-3xl lg:text-4xl">
			Gravity Resin Company?
			<Hr
				id="small"
				borderColor="border-slate-600 "
				options={{
					rootMargin: '-10px',
					unobserveOnEnter: true
				}}
			/>
		</h2>
		<p class="text-bold my-8 mr-0 whitespace-pre-line text-pretty text-3xl tracking-tighter">
			In our world, we create timeless masterpieces from visions. We make the difference, and you
			make the impossible.
		</p>
	</div>
</section>

<section class="my-40 h-[40vh]">
	<div class="mx-0 flex h-full w-full flex-col md:flex-row">
		<div class="order-2 flex h-full items-center p-6 md:order-1 md:basis-[40%]">
			<div class="w-full">
				<BlureFade>
					<h1 class="text-2xl font-semibold tracking-tight sm:text-3xl lg:text-4xl">
						Artistic Section:
					</h1>
					<br />
					<h2 class=" w-fit text-2xl font-semibold tracking-tight sm:text-3xl lg:text-4xl">
						What do we offer to artists and creatives?
					</h2>
					<p class="text-bold my-6 text-pretty text-xl tracking-tighter md:my-8 md:text-2xl">
						In our world, we create timeless masterpieces from visions. We make the difference, and
						you make the impossible.
					</p>
				</BlureFade>
			</div>
		</div>
		<div class=" order-1 h-full w-screen md:order-2 md:h-[40vh] md:flex-1">
			<img
				src="art/art.jpg"
				alt="Resin Artist "
				class="h-full w-full border-none object-cover object-center"
			/>
		</div>
	</div>
</section>
<section class="h-[60vh] w-full">s</section>

<style>
	.myshadow {
		text-shadow: 2px 2px #a7158093;
	}
</style>
