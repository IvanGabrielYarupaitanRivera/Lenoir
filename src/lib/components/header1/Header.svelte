<script lang="ts">
	import Logo from './Logo.svelte';
	import Navigation from './Navigation.svelte';
</script>

<header class="w-full border-b border-gray-200 shadow-lg">
	<!-- Fila 1: Branding -->
	<div class="bg-black bg-gradient-to-bl to-yellow-950 py-4 lg:py-6">
		<div class="container mx-auto px-4">
			<Logo />
		</div>
	</div>

	<!-- Fila 2: Navegación -->
	<div class="bg-white py-3">
		<div class="container mx-auto px-4">
			<Navigation />
		</div>
	</div>
</header>
