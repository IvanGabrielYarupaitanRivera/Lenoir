<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	interface SEOProps {
		title?: string;
		description?: string;
		keywords?: string;
		author?: string;
		type?: 'website' | 'product' | 'article';
		image?: string;
		url?: string;
		siteName?: string;
		locale?: string;
		noindex?: boolean;
		nofollow?: boolean;
	}

	let {
		title = 'Lenoir - Corbatas Elegantes',
		description = 'Descubre nuestra colección de corbatas elegantes y sofisticadas. Productos de alta calidad para complementar tu estilo profesional.',
		keywords = 'corbatas, corbatas elegantes, accesorios masculinos, moda formal, corbatas de lujo',
		author = 'Lenoir',
		type = 'website',
		image = 'https://lenoir.click/images/og-image.jpg',
		url = 'https://lenoir.click/',
		siteName = 'Lenoir',
		locale = 'es_ES',
		noindex = false,
		nofollow = false
	}: SEOProps = $props();

	// Construir el robots content
	const robotsContent = [
		...(noindex ? ['noindex'] : ['index']),
		...(nofollow ? ['nofollow'] : ['follow'])
	].join(', ');

	// Datos estructurados JSON-LD para portal de consulta jurídica
	const structuredData = {
		'@context': 'https://schema.org',
		'@type': 'Store',
		name: 'Lenoir',
		description: description,
		url: url,
		image: image,
		mainEntityOfPage: {
			'@type': 'WebPage',
			'@id': url
		},
		potentialAction: {
			'@type': 'SearchAction',
			target: url + '/search?q={search_term_string}',
			'query-input': 'required name=search_term_string'
		}
	};
</script>

<svelte:head>
	<!-- Título -->
	<title>{title}</title>

	<!-- Meta tags básicos -->
	<meta name="description" content={description} />
	<meta name="keywords" content={keywords} />
	<meta name="author" content={author} />
	<meta name="robots" content={robotsContent} />
	<meta name="googlebot" content={robotsContent} />

	<!-- Meta tags de idioma y región -->
	<meta name="language" content="Spanish" />

	<!-- Open Graph / Facebook -->
	<meta property="og:type" content={type} />
	<meta property="og:title" content={title} />
	<meta property="og:description" content={description} />
	<meta property="og:image" content={image} />
	<meta property="og:url" content={url} />
	<meta property="og:site_name" content={siteName} />
	<meta property="og:locale" content={locale} />

	<!-- Twitter Card -->
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content={title} />
	<meta name="twitter:description" content={description} />
	<meta name="twitter:image" content={image} />

	<!-- Canonical URL -->
	<link rel="canonical" href={url} />

	<!-- Datos estructurados JSON-LD -->
	{@html `<script type="application/ld+json">${JSON.stringify(structuredData)}</script>`}

	<!-- Favicon y iconos -->
	<link rel="icon" href={favicon} type="image/svg+xml" />
	<link rel="apple-touch-icon" href={favicon} />
	<meta name="theme-color" content="#D4AF37" />
</svelte:head>
