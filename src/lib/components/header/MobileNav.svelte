<script lang="ts">
	import { ShoppingCart, X, Menu } from '@lucide/svelte';

	let {
		isMobileMenuOpen,
		toggleMobileMenu,
		openWhatsApp
	}: {
		isMobileMenuOpen: boolean;
		toggleMobileMenu: () => void;
		openWhatsApp: () => void;
	} = $props();
</script>

<div class="ml-auto flex items-center space-x-4 lg:hidden">
	<button
		onclick={openWhatsApp}
		class="p-2 text-yellow-600 transition-transform duration-200 hover:scale-110 active:scale-95"
		aria-label="Consultar por WhatsApp"
	>
		<ShoppingCart size={24} />
	</button>

	<button
		onclick={toggleMobileMenu}
		class="p-2 text-yellow-600 transition-all duration-200 hover:scale-110 active:scale-95"
		aria-label={isMobileMenuOpen ? 'Cerrar menú' : 'Abrir menú'}
	>
		{#if isMobileMenuOpen}
			<X size={24} />
		{:else}
			<Menu size={24} />
		{/if}
	</button>
</div>
