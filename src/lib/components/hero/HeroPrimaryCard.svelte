<script lang="ts">
	import { ArrowRight } from '@lucide/svelte';
	import LogoCompleto from '$lib/assets/logo-completo.svg';

	const title = 'Elegancia que Define tu Estilo';
	const subtitle =
		'Descubre nuestra colección exclusiva de corbatas premium diseñadas para el caballero moderno que busca distinción y sofisticación.';
	const ctaText = 'Ver Colección';
	const ctaHref = '/productos';
	const logoAlt = 'Lenoir';
</script>

<article
	class="group relative flex flex-col overflow-hidden rounded-2xl bg-[url(https://images.unsplash.com/photo-1506463108611-88834e9f6169?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)] p-6 shadow-lg transition-all duration-500 hover:shadow-2xl lg:p-10"
>
	<!-- Overlay oscuro para legibilidad -->
	<div class="absolute inset-0 bg-gradient-to-br from-black via-black/80 to-black/60"></div>

	<!-- Logo -->
	<div class="relative z-10 mb-6">
		<img
			src={LogoCompleto}
			alt={logoAlt}
			class="h-auto w-12 object-contain transition-transform duration-500 group-hover:scale-105 lg:w-16"
		/>
	</div>

	<!-- Contenido -->
	<div class="relative z-10 mt-auto space-y-4">
		<h1
			class="text-3xl leading-tight font-bold text-white transition-colors duration-300 lg:text-4xl"
		>
			{title}
		</h1>

		<p class="max-w-lg text-base text-gray-300">
			{subtitle}
		</p>

		<a
			href={ctaHref}
			class="inline-flex cursor-pointer items-center gap-2.5 rounded-xl bg-yellow-600 px-6 py-3.5 font-semibold text-white shadow-lg transition-all duration-300 hover:scale-105 hover:bg-yellow-500 hover:shadow-2xl active:scale-95"
		>
			<span class="text-sm">{ctaText}</span>
			<ArrowRight size={20} class="transition-transform duration-300 group-hover:translate-x-1" />
		</a>
	</div>
</article>
