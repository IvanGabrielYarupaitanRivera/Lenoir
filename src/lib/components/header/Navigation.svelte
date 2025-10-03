<script lang="ts">
	import { page } from '$app/state';
	import MobileMenu from './MobileMenu.svelte';
	import DesktopNav from './DesktopNav.svelte';
	import MobileNav from './MobileNav.svelte';

	let isMobileMenuOpen = $state(false);

	const menuItems = [
		{ label: 'Inicio', href: '/' },
		{ label: 'Productos', href: '/productos' },
		{ label: 'Sobre Nosotros', href: '/sobre-nosotros' },
		{ label: 'Contacto', href: '/contacto' }
	];

	function toggleMobileMenu() {
		isMobileMenuOpen = !isMobileMenuOpen;
	}

	function openWhatsApp() {
		const message = encodeURIComponent('Hola, me interesa conocer más sobre sus productos.');
		window.open(`https://wa.me/+51971030722?text=${message}`, '_blank');
	}
</script>

<nav class="flex items-center justify-between">
	<DesktopNav {menuItems} currentPath={page.url.pathname} {openWhatsApp} />
	<MobileNav {isMobileMenuOpen} {toggleMobileMenu} {openWhatsApp} />
</nav>

<!-- Mobile Menu -->
{#if isMobileMenuOpen}
	<MobileMenu {menuItems} currentPath={page.url.pathname} onClose={toggleMobileMenu} />
{/if}
