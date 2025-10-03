<script lang="ts">
	import HeroSection from '$lib/components/hero/HeroSection.svelte';

	const heroData = {
		featured: {
			id: '1',
			name: 'Corbata Seda Premium',
			image: 'https://images.unsplash.com/photo-1617127365659-c47fa864d8bc?w=800&q=80',
			isNew: true
		},
		showcase: [
			{
				id: '2',
				name: 'Corbata Clásica',
				image:
					'https://images.unsplash.com/photo-1707177197994-153e671df346?q=80&w=2080&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
			},
			{
				id: '3',
				name: 'Corbata Moderna',
				image:
					'https://images.unsplash.com/photo-1564866979596-b04d38c149c1?q=80&w=880&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
			},
			{
				id: '4',
				name: 'Corbata Executive',
				image:
					'https://images.unsplash.com/photo-1658500140897-7f2a772391e3?q=80&w=880&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
			}
		]
	};
</script>

<HeroSection data={heroData} />
