<script lang="ts">
	import Logo from './Logo.svelte';
	import SocialLinks from './SocialLinks.svelte';
	import FooterLinks from './FooterLinks.svelte';
	import Copyright from './Copyright.svelte';
</script>

<footer class="bg-black text-white">
	<!-- Main Footer Content -->
	<div class="container mx-auto px-4 py-12">
		<div class="grid grid-cols-1 gap-8 lg:grid-cols-4">
			<!-- Brand Section -->
			<div class="space-y-4 lg:col-span-2">
				<Logo />
				<p class="mb-4 max-w-md text-gray-400">
					Descubre nuestra colección de corbatas elegantes y sofisticadas. Productos de alta calidad
					para complementar tu estilo profesional.
				</p>
				<SocialLinks />
			</div>

			<!-- Quick Links -->
			<FooterLinks />
		</div>
	</div>

	<!-- Bottom Bar -->
	<div class="border-t border-gray-800">
		<div class="container mx-auto px-4 py-6">
			<Copyright />
		</div>
	</div>
</footer>
