<script lang="ts">
	import { MessageCircle, Sparkles } from '@lucide/svelte';

	interface Product {
		id: string;
		name: string;
		image: string;
		isNew?: boolean;
	}

	let { product }: { product: Product } = $props();

	function openWhatsApp() {
		const message = encodeURIComponent(`Hola, me interesa el producto: ${product.name}`);
		window.open(`https://wa.me/+51971030722?text=${message}`, '_blank');
	}
</script>

<article
	class="group relative flex flex-col overflow-hidden rounded-2xl shadow-lg transition-all duration-500 hover:shadow-2xl"
>
	<!-- Badge "Nuevo" -->
	{#if product.isNew}
		<div
			class="absolute top-4 left-4 z-20 flex items-center gap-1.5 rounded-full bg-yellow-600 px-3 py-1.5 shadow-lg backdrop-blur-sm transition-all duration-300 group-hover:scale-105"
		>
			<Sparkles size={14} class="text-white" />
			<span class="text-xs font-semibold tracking-wide text-white uppercase">Nuevo</span>
		</div>
	{/if}

	<!-- Imagen del producto -->
	<div class="relative aspect-square overflow-hidden">
		<img
			src={product.image}
			alt={product.name}
			class="h-full w-full object-cover transition-all duration-700 group-hover:scale-110"
			loading="lazy"
		/>
		<!-- Overlay gradient mejorado -->
		<div
			class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/50 to-transparent opacity-90 transition-opacity duration-500 group-hover:opacity-100"
		></div>

		<!-- Efecto de brillo en hover -->
		<div
			class="absolute inset-0 bg-gradient-to-tr from-transparent via-white/0 to-white/0 opacity-0 transition-opacity duration-500 group-hover:via-white/5 group-hover:opacity-100"
		></div>
	</div>

	<!-- Contenido sobrepuesto -->
	<div
		class="absolute right-0 bottom-0 left-0 z-10 flex flex-col justify-end p-6 transition-transform duration-500 group-hover:translate-y-0 lg:p-8"
	>
		<div class="mb-4 transform transition-all duration-500 group-hover:translate-y-0">
			<h3
				class="mb-2 text-xl leading-tight font-bold text-white transition-all duration-300 group-hover:text-yellow-500 lg:text-2xl"
			>
				{product.name}
			</h3>
			<p class="text-sm font-medium tracking-wider text-gray-200 uppercase lg:text-base">
				Producto destacado
			</p>
		</div>

		<!-- Botón WhatsApp mejorado -->
		<button
			onclick={openWhatsApp}
			class="flex cursor-pointer items-center justify-center gap-2.5 rounded-xl bg-yellow-600 px-5 py-3.5 font-semibold text-white shadow-lg transition-all duration-300 hover:scale-[1.02] hover:bg-yellow-500 hover:shadow-2xl active:scale-95 lg:px-6 lg:py-4"
		>
			<MessageCircle size={20} class="transition-transform duration-300 group-hover:rotate-12" />
			<span class="text-sm lg:text-base">Consultar por WhatsApp</span>
		</button>
	</div>
</article>
