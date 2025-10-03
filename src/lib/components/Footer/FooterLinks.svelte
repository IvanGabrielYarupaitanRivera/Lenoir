<script lang="ts">
	const linkGroups = [
		{
			title: 'Navegación',
			links: [
				{ label: 'Inicio', href: '/' },
				{ label: 'Productos', href: '/productos' },
				{ label: 'Sobre Nosotros', href: '/sobre-nosotros' },
				{ label: 'Contacto', href: '/contacto' }
			]
		},
		{
			title: 'Legal',
			links: [
				{ label: 'Términos y Condiciones', href: '/terminos' },
				{ label: 'Política de Privacidad', href: '/privacidad' }
			]
		}
	];
</script>

{#each linkGroups as group}
	<div>
		<h3 class="mb-4 text-lg font-semibold text-white">{group.title}</h3>
		<ul class="space-y-2">
			{#each group.links as link}
				<li>
					<a
						href={link.href}
						class="cursor-pointer text-gray-400 transition-colors duration-200 hover:text-yellow-500"
					>
						{link.label}
					</a>
				</li>
			{/each}
		</ul>
	</div>
{/each}
