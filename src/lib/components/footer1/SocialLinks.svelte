<script lang="ts">
	import { Facebook, Instagram, Mail } from '@lucide/svelte';

	const socialLinks = [
		{
			name: 'Facebook',
			icon: Facebook,
			href: 'https://facebook.com/lenoir',
			ariaLabel: 'Visita nuestro Facebook'
		},
		{
			name: 'Instagram',
			icon: Instagram,
			href: 'https://instagram.com/lenoir',
			ariaLabel: 'Visita nuestro Instagram'
		},
		{
			name: 'Email',
			icon: Mail,
			href: 'mailto:contacto@lenoir.com',
			ariaLabel: 'Envíanos un correo'
		}
	];
</script>

<div class="flex items-center space-x-4">
	{#each socialLinks as social}
		<a
			href={social.href}
			target="_blank"
			rel="noopener noreferrer"
			aria-label={social.ariaLabel}
			class="cursor-pointer rounded-full bg-gray-800 p-3 text-gray-400 transition-all duration-200 hover:scale-110 hover:bg-yellow-600 hover:text-white active:scale-95"
		>
			<social.icon size={20} />
		</a>
	{/each}
</div>
