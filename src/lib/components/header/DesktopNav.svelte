<script lang="ts">
	import { ShoppingCart } from '@lucide/svelte';
	import Logo from '$lib/assets/logo.svg';

	interface MenuItem {
		label: string;
		href: string;
	}

	let {
		menuItems,
		currentPath,
		openWhatsApp
	}: {
		menuItems: MenuItem[];
		currentPath: string;
		openWhatsApp: () => void;
	} = $props();
</script>

<!-- Contenedor principal: logo | nav | botón -->
<div class="hidden w-full items-center justify-between lg:flex">
	<!-- Logo -->
	<div class="flex-shrink-0">
		<img src={Logo} alt="Lenoir Logo" class="h-12" />
	</div>

	<!-- Navegación centrada -->
	<nav class="flex flex-1 items-center justify-center space-x-8">
		{#each menuItems as item}
			<a
				href={item.href}
				class="group relative font-medium text-white transition-colors duration-300 hover:text-yellow-600 {currentPath ===
				item.href
					? 'text-yellow-500'
					: ''}"
			>
				{item.label}
				<span
					class="absolute bottom-0 left-0 h-0.5 bg-yellow-500 transition-all duration-300 {currentPath ===
					item.href
						? 'w-full'
						: 'w-0 group-hover:w-full'}"
				></span>
			</a>
		{/each}
	</nav>

	<!-- Botón de consulta -->
	<div class="flex-shrink-0">
		<button
			onclick={openWhatsApp}
			class="flex items-center space-x-2 rounded-lg bg-yellow-600 px-6 py-3 font-medium text-white shadow-lg transition-all duration-300 hover:scale-105 hover:bg-yellow-500 hover:shadow-xl active:scale-95"
		>
			<ShoppingCart size={20} />
			<span>Consultar</span>
		</button>
	</div>
</div>
