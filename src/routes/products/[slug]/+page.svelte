<script>
	let { data } = $props();

    let product = $derived(data.product);
</script>

<svelte:head>
	<title>Ergit's Webshop - {product.name}</title>
	<meta name="description" content={product.description} />
	<meta property="og:title" content={product.name} />
	<meta property="og:image" content={product.image_url} />
</svelte:head>

<main class="min-h-screen bg-gray-50 flex items-center justify-center p-6">
	<div class="bg-white rounded-xl shadow-md max-w-4xl w-full grid md:grid-cols-2 overflow-hidden">


		<div>
			<img
				src={product.image_url}
				alt={product.name}
				class="w-full h-full object-cover"
			/>
		</div>


		<div class="p-6 flex flex-col justify-between">
			<div>
				<h1 class="text-2xl font-bold text-gray-800">
					{product.name}
				</h1>

				<p class="text-gray-600 mt-4">
					{product.description}
				</p>
			</div>

			<div class="mt-6">
				<p class="text-2xl font-bold text-green-600">
					${product.price}
				</p>

               <div class="flex items-center justify-center gap-4 mt-6">
                    <button class="px-6 py-2 bg-black text-white rounded-lg hover:bg-gray-800 transition">
                        Buy Now
                    </button>

                    <a 
                        href="/products"
                        class="px-6 py-2 border border-gray-300 rounded-lg hover:bg-gray-100 transition text-gray-700"
                    >
                        Go Back
                    </a>
                </div>
			</div>
		</div>

	</div>
</main>