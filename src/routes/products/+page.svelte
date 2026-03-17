<script>
	import background from '$lib/assets/device.jpg';
	let { data } = $props();
</script>

<svelte:head>
	<title>Ergit's Webshop - Electronics for all!</title>
	<meta name="description" content="We sell used electronics for a super cheap price!" />
	<meta property="og:title" content="Ergit's Webshop - Electronics for all!" />
	<meta property="og:image" content={background} />
</svelte:head>


<header
	class="relative h-100 flex items-center justify-center text-center text-white bg-cover bg-center"
	style="background-image:url(https://res.cloudinary.com/dgyaze36s/image/upload/w_1080,h_1080,c_fill,q_auto/v1772711357/device_naqz6u.jpg)"
>
	<div class="absolute inset-0 bg-black/60"></div>

	<div class="relative z-10 px-4">
		<h1 class="text-4xl md:text-5xl font-extrabold">
			Electronic Devices
		</h1>
		<p class="mt-4 text-lg text-gray-200 max-w-xl mx-auto">
			Affordable, high-quality used electronics for everyone.
		</p>
	</div>
</header>


<main class="bg-gray-50 min-h-screen">
	<div class="max-w-7xl mx-auto px-6 py-10">

		<h2 class="text-2xl font-bold text-gray-800 mb-6">
			Latest Products
		</h2>

		<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
			{#each data.products as product (product.id)}
				<a
					href={`/products/${product.slug}`}
					class="bg-white rounded-2xl shadow-md hover:shadow-xl transition overflow-hidden group"
				>
					<div class="overflow-hidden">
						<img
							src={product.image_url}
							alt={product.name}
							class="w-full h-48 object-cover group-hover:scale-105 transition duration-300"
						/>
					</div>

					<div class="p-4">
						<h2 class="text-lg font-semibold text-gray-800">
							{product.name}
						</h2>

						<p class="text-sm text-gray-500 mt-2 line-clamp-2">
							{product.description}
						</p>

						<div class="mt-4 flex items-center justify-between">
							<span class="text-lg font-bold text-green-600">
								${product.price}
							</span>

							<button
								class="px-3 py-1.5 text-sm bg-black text-white rounded-lg hover:bg-gray-800 transition"
							>
								Buy
							</button>
						</div>
					</div>
				</a>
			{/each}
		</div>

	</div>
</main>


<footer class="bg-blue-950 text-gray-200">
	<div class="max-w-7xl mx-auto px-6 py-10 grid grid-cols-1 md:grid-cols-3 gap-8">

		<div>
			<h3 class="text-xl font-bold text-white">Ergit's Webshop</h3>
			<p class="mt-3 text-sm text-gray-400">
				Your trusted place for affordable electronics. Quality devices at prices everyone can afford.
			</p>
		</div>


		<div>
			<h4 class="font-semibold text-white mb-3">Quick Links</h4>
			<ul class="space-y-2 text-sm">
				<li><a href="/products" class="hover:text-white">Products</a></li>
				<li><a href="/" class="hover:text-white">About</a></li>
				<li><a href="/" class="hover:text-white">Contact</a></li>
			</ul>
		</div>


		<div>
			<h4 class="font-semibold text-white mb-3">Contact</h4>
			<p class="text-sm text-gray-400">Email: ergitbeqiri07@gmail.com</p>
			<p class="text-sm text-gray-400 mt-2">Location: Europe</p>
		</div>

	</div>

	<div class="border-t border-gray-700 text-center text-sm py-4 text-gray-400">
		© {new Date().getFullYear()} Ergit's Webshop. All rights reserved.
	</div>
</footer>