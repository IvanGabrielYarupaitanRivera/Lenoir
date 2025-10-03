<script lang="ts">
	import { Users, Truck, Award, Shield, Star, Package } from '@lucide/svelte';
	import type { Component } from 'svelte';

	interface TrustItem {
		icon: Component;
		value: string;
		label: string;
	}

	const trustItems: TrustItem[] = [
		{
			icon: Users,
			value: '100+',
			label: 'Clientes Satisfechos'
		},
		{
			icon: Truck,
			value: 'Nacional',
			label: 'Envíos a Todo el País'
		},
		{
			icon: Award,
			value: 'Premium',
			label: 'Calidad Garantizada'
		}
	];
</script>

<aside
	class="group relative overflow-hidden rounded-2xl border border-gray-200 bg-gradient-to-br from-white via-gray-50 to-white p-8 shadow-lg transition-all duration-500 hover:shadow-2xl lg:p-10"
	aria-label="Indicadores de confianza"
>
	<!-- Decoración de fondo -->
	<div
		class="absolute -top-10 -right-10 h-40 w-40 rounded-full bg-yellow-600/5 blur-3xl transition-all duration-500 group-hover:scale-150"
	></div>
	<div
		class="absolute -bottom-10 -left-10 h-40 w-40 rounded-full bg-yellow-600/5 blur-3xl transition-all duration-500 group-hover:scale-150"
	></div>

	<!-- Contenido -->
	<div class="relative z-10">
		<!-- Grid de items -->
		<dl class="grid grid-cols-1 gap-8 md:grid-cols-3 md:gap-10">
			{#each trustItems as item}
				<div
					class="group/item relative flex flex-col items-center text-center transition-transform duration-300"
				>
					<!-- Ícono -->
					<div
						class="mb-4 flex h-16 w-16 items-center justify-center rounded-2xl bg-gradient-to-br from-yellow-600 to-yellow-500 text-white shadow-lg transition-all duration-300 group-hover/item:scale-110 group-hover/item:shadow-2xl lg:h-20 lg:w-20"
					>
						<item.icon size={32} class="lg:h-10 lg:w-10" />
					</div>

					<!-- Valor y Label -->
					<dt>
						<p
							class="mb-1 text-3xl font-bold text-black transition-colors duration-300 group-hover/item:text-yellow-600 lg:text-4xl"
						>
							{item.value}
						</p>
						<p class="mb-2 text-base font-semibold text-gray-600 lg:text-lg">
							{item.label}
						</p>
					</dt>

					<!-- Línea decorativa en hover -->
					<div
						class="absolute -bottom-2 left-1/2 h-1 w-0 -translate-x-1/2 rounded-full bg-yellow-600 transition-all duration-300 group-hover/item:w-16"
					></div>
				</div>
			{/each}
		</dl>
	</div>
</aside>
