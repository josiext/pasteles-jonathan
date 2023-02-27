<script lang="ts">
	export let products: { name: string; price: number; image: string }[] = [];
</script>

<div class="bg-[#f8f8f8] min-h-screen w-full py-32" id="catalog">
	<h1 class="text-[58px] font-semibold text-center pb-32">Catalogo</h1>

	<div class="max-w-[1200px] mx-auto gap-12 flex flex-wrap justify-center">
		{#each products as { name, price, image }}
			<div
				class="flex-col items-center rounded-xl overflow-hidden w-[300px] bg-[#F4F2F3] border-4 border-[#ECECEC] border-r-[#F1F1F1] "
			>
				<img src={image} class="w-full h-48 object-cover " alt={name} />
				<h2 class="text-2xl p-6 font-semibold text-center text-gray-600">{name}</h2>
				<p class="text-2xl  p-6 font-semibold text-center text-gray-600">{price}</p>
			</div>
		{/each}
	</div>
</div>
