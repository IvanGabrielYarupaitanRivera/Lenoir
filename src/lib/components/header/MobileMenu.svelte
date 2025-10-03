<script lang="ts">
	import { slide, fade } from 'svelte/transition';
	import { X } from '@lucide/svelte';

	interface MobileMenuProps {
		menuItems: Array<{ label: string; href: string }>;
		currentPath: string;
		onClose: () => void;
	}

	let { menuItems, currentPath, onClose }: MobileMenuProps = $props();

	function handleMenuClick() {
		onClose();
	}
</script>

<!-- Overlay -->
<button
	class="fixed inset-0 z-40 bg-black/60 backdrop-blur-sm lg:hidden"
	transition:fade={{ duration: 200 }}
	onclick={onClose}
	aria-label="Cerrar menú"
></button>

<!-- Mobile Menu Panel -->
<div
	class="fixed top-0 right-0 z-50 h-full w-80 bg-white shadow-2xl lg:hidden"
	transition:slide={{ duration: 300, axis: 'x' }}
>
	<!-- Header del menú -->
	<div class="flex items-center justify-between border-b border-gray-200 p-6">
		<h2 class="text-xl font-bold text-black">Menú</h2>
		<button
			onclick={onClose}
			class="cursor-pointer rounded-full p-2 text-black transition-all duration-200 hover:bg-gray-100 hover:text-yellow-600 active:scale-95"
			aria-label="Cerrar menú"
		>
			<X size={24} />
		</button>
	</div>

	<!-- Navegación -->
	<nav class="space-y-2 p-6">
		{#each menuItems as item}
			<a
				href={item.href}
				onclick={handleMenuClick}
				class="group relative block cursor-pointer rounded-lg px-4 py-3 text-lg font-medium transition-all duration-200
                    {currentPath === item.href
					? 'bg-yellow-50 text-yellow-600'
					: 'text-black hover:bg-gray-50 hover:text-yellow-600'}"
			>
				<span class="relative z-10">{item.label}</span>
				{#if currentPath === item.href}
					<span
						class="absolute top-1/2 left-0 h-8 w-1 -translate-y-1/2 rounded-r-full bg-yellow-600"
					></span>
				{/if}
			</a>
		{/each}
	</nav>
</div>
