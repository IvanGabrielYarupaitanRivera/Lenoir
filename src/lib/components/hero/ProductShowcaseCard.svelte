<script lang="ts">
	interface Product {
		id: string;
		name: string;
		image: string;
	}

	let { product }: { product: Product } = $props();
</script>

<a
	href="/productos/{product.id}"
	class="group relative block cursor-pointer overflow-hidden rounded-2xl bg-white shadow-md transition-all duration-300 hover:scale-105 hover:shadow-xl"
>
	<!-- Imagen del producto -->
	<div class="relative aspect-square overflow-hidden bg-gray-100">
		<img
			src={product.image}
			alt={product.name}
			class="h-full w-full object-cover transition-transform duration-500 group-hover:scale-110"
			loading="lazy"
		/>

		<!-- Overlay dorado en hover -->
		<div
			class="absolute inset-0 bg-yellow-800/20 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
		></div>
	</div>

	<!-- Nombre del producto -->
	<div class="p-4">
		<h3
			class="text-center text-base font-semibold text-black transition-colors duration-300 group-hover:text-yellow-600 lg:text-lg"
		>
			{product.name}
		</h3>
	</div>

	<!-- Indicador visual hover -->
	<div
		class="absolute bottom-0 left-0 h-1 w-0 bg-yellow-800 transition-all duration-300 group-hover:w-full"
	></div>
</a>
