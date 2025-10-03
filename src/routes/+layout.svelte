<script lang="ts">
	import '../app.css';
	import SEO from '$lib/components/SEO.svelte';
	import Header from '$lib/components/header/Header.svelte';
	import Footer from '$lib/components/footer/Footer.svelte';

	let { children } = $props();
</script>

<!-- Componente SEO -->
<SEO />

<!-- Header -->
<Header />

{@render children?.()}

<!-- Footer -->
<Footer />
