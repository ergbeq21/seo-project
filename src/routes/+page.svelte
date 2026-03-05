<script>
    import background from '$lib/assets/device.jpg'

    let { data } = $props();
</script>


<svelte:head>
    <title>Ergit's Webshop - Electronics for all!</title>
    <meta name="description" content="We sell used electronics for a super cheap price!"/>
    <meta property="og:title" content="Ergit's Webshop - Electronics for all!">
    <meta property="og:image" content="{background}">
</svelte:head>

<header class="h-125 bg-center font-extrabold text-white bg-cover flex items-center justify-center" style="background-image:url(https://res.cloudinary.com/dgyaze36s/image/upload/w_256,h_256,c_fill,q_auto/v1772711357/device_naqz6u.jpg)">
    <h1 class="text-5xl">Electronic Devices</h1>
</header>

<main>

    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6 p-6">
        {#each data.products as product (product.id)}
            <div class="bg-white rounded-xl shadow-md hover:shadow-xl transition overflow-hidden">
                
                <img
                    src={product.image_url}
                    alt={product.name}
                    class="w-full h-48 object-cover"
                />

                <div class="p-4">
                    <h2 class="text-lg font-semibold text-gray-800">
                        {product.name}
                    </h2>

                    <p class="text-sm text-gray-500 mt-2">
                        {product.description}
                    </p>

                    <div class="mt-4 flex items-center justify-between">
                        <span class="text-lg font-bold text-green-600">
                            ${product.price}
                        </span>

                        <button class="px-3 py-1.5 text-sm bg-black text-white rounded-lg hover:bg-gray-800 transition">
                            Buy
                        </button>
                    </div>
                </div>

            </div>
        {/each}
    </div>

</main>


<footer class="h-75 bg-blue-950 text-white flex items-center justify-center">

</footer>
