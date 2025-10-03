<script lang="ts">
	import { ShoppingCart } from '@lucide/svelte';

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

<div class="hidden flex-1 items-center justify-center lg:flex">
	<nav class="flex items-center space-x-10">
		{#each menuItems as item}
			<a
				href={item.href}
				class="group relative cursor-pointer font-medium text-black transition-all duration-300 hover:text-yellow-600
                    {currentPath === item.href ? 'text-yellow-600' : ''}"
			>
				{item.label}
				<span
					class="absolute bottom-0 left-0 h-0.5 w-0 bg-yellow-600 transition-all duration-300 group-hover:w-full
                        {currentPath === item.href ? 'w-full' : ''}"
				></span>
			</a>
		{/each}
	</nav>
</div>

<button
	onclick={openWhatsApp}
	class="hidden cursor-pointer items-center space-x-2 rounded-lg bg-yellow-600 px-6 py-3 font-medium text-white shadow-lg transition-all duration-300 hover:scale-105 hover:bg-yellow-500 hover:shadow-xl active:scale-95 lg:flex"
>
	<ShoppingCart size={20} />
	<span>Consultar</span>
</button>
