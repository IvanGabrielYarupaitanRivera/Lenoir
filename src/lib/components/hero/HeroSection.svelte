<script lang="ts">
	import HeroPrimaryCard from './HeroPrimaryCard.svelte';
	import FeaturedProductCard from './FeaturedProductCard.svelte';
	import TrustBanner from './TrustBanner.svelte';
	import ProductShowcaseCard from './ProductShowcaseCard.svelte';

	interface HeroData {
		featured: {
			id: string;
			name: string;
			image: string;
			isNew?: boolean;
		};
		showcase: Array<{
			id: string;
			name: string;
			image: string;
		}>;
	}

	let { data }: { data: HeroData } = $props();
</script>

<section class="bg-gray-50 py-8 lg:py-16">
	<div class="container mx-auto px-4">
		<!-- Bento Grid -->
		<div class="grid grid-cols-1 gap-4 lg:grid-cols-12 lg:gap-6">
			<!-- Hero Primary Card - Mobile: full width, Desktop: 8 cols, 2 rows -->
			<div class="lg:col-span-8 lg:row-span-2">
				<HeroPrimaryCard />
			</div>

			<!-- Featured Product Card - Mobile: full width, Desktop: 4 cols, 2 rows -->
			<div class="lg:col-span-4 lg:row-span-2">
				<FeaturedProductCard product={data.featured} />
			</div>

			<!-- Trust Banner - Mobile: full width, Desktop: 12 cols, 1 row -->
			<div class="lg:col-span-12">
				<TrustBanner />
			</div>
			<!-- Product Showcase Cards - Mobile: full width, Desktop: 4 cols each -->
			{#each data.showcase as product}
				<div class="lg:col-span-4">
					<ProductShowcaseCard {product} />
				</div>
			{/each}
		</div>
	</div>
</section>
