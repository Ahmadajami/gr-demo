<script lang="ts">
	import { ChartBar, Lightbulb, TrendingUp, ChevronRight } from '@lucide/svelte';
	import * as Card from '$lib/components/ui/card';
	import Button from '$lib/components/ui/button/button.svelte';
	import { Input } from '$lib/components/ui/input';
	import { Textarea } from '$lib/components/ui/textarea';
	import { Label } from '$lib/components/ui/label';
	import Carousel from '$lib/components/Carousel.svelte';
	import BlureFade from '$lib/BlureFade.svelte';
	import Hr from '$lib/components/HR.svelte';
	import BentoGrid from '$lib/components/layout/Grid/BentoGrid.svelte';

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

<!-- Hero Section -->
<section class="relative overflow-hidden px-4 py-16 sm:px-6 lg:px-8">
	<div class="container mx-auto">
		<div class="grid items-center gap-12 lg:grid-cols-2 lg:gap-16">
			<!-- Text Content -->
			<div
				class="order-2 flex flex-col items-center text-center lg:order-1 lg:items-start lg:text-left"
			>
				<BlureFade>
					<h1 class="myshadow text-4xl font-bold tracking-tight sm:text-5xl lg:text-6xl">
						Welcome To<br />
						Graffiti Resin World.
					</h1>
				</BlureFade>
				<Hr id="sme" />
				<BlureFade>
					<p class="mt-6 text-lg leading-relaxed text-muted-foreground">
						Graffiti Design is not just a company; it's a passion embodied in every design. We
						believe that creativity knows no bounds, and we strive to transform your visions into
						masterpieces that touch hearts and inspire minds. Discover our world filled with colors
						and innovative ideas, and let's make your own mark on this world together.
					</p>
				</BlureFade>
			</div>

			<!-- Image -->
			<div class="order-1 lg:order-2">
				<div class="relative z-10 max-w-[600px]">
					<Carousel />
				</div>
			</div>
		</div>
	</div>
</section>

<section class="mt-12 flex flex-col px-4 py-20 lg:px-8">
	<BlureFade delay={0.2}>
		<h1 class=" myshadow ml-11 w-fit text-4xl font-bold tracking-tight sm:text-5xl lg:text-6xl">
			Our departments<br />
			<Hr
				id="text"
				options={{
					rootMargin: '-10px',
					unobserveOnEnter: false
				}}
			/>
		</h1>
	</BlureFade>

	<article class="container mt-8 h-96">
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
		<p class="text-bold my-8 mr-0 text-pretty text-3xl tracking-tighter">
			In our world, we create timeless masterpieces from visions. We make the difference, and you
			make the impossible.
		</p>
	</div>
</section>
<section class="my-24">
	<div class=" flex h-[40vh] flex-row">
		<div class="basis-3/6">
			<div class="container mx-auto px-4">
				<h1 class="text-2xl font-semibold tracking-tight sm:text-3xl lg:text-4xl">
					Artistic Section:
				</h1>
				<br />
				<h2 class=" w-fit text-2xl font-semibold tracking-tight sm:text-3xl lg:text-4xl">
					What do we offer to artists and creatives?
					<Hr
						id="small"
						borderColor="border-slate-600 "
						options={{
							rootMargin: '-90px',
							unobserveOnEnter: true
						}}
					/>
				</h2>
				<p class="text-bold my-8 mr-0 text-pretty text-3xl tracking-tighter">
					In our world, we create timeless masterpieces from visions. We make the difference, and
					you make the impossible.
				</p>
			</div>
		</div>
		<div class="basis-4/6 rounded-md shadow-2xl shadow-black">
			<img
				class="h-full w-full object-cover object-center"
				src="https://images.unsplash.com/photo-1624813535022-97635d828ac5?q=80&w=2159&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
				alt="Resin Natural"
			/>
		</div>
	</div>
</section>

<style>
	.myshadow {
		text-shadow: 2px 2px #a71580;
	}
</style>
