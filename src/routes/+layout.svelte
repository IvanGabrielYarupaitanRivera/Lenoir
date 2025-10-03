<script lang="ts">
	import '../app.css';
	import SEO from '$lib/components/SEO.svelte';
	import Header from '$lib/components/Header/Header.svelte';
	import Footer from '$lib/components/Footer/Footer.svelte';

	let { children } = $props();
</script>

<!-- Componente SEO -->
<SEO />

<!-- Header -->
<Header />

{@render children?.()}

<!-- Footer -->
<Footer />
