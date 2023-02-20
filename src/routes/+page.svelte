<script>
  import { onMount } from "svelte";
    import axios from "axios";
    import Papa from "papaparse";

    /**
   * @type {any[]}
   */   
        let products = [];

    onMount(async () => {
        const response = await axios.get("https://docs.google.com/spreadsheets/d/e/2PACX-1vSlTuh4wcDhnwmHdgzkyD1rNI_HeCy2Hhha5gu237IxiYB7MQEb4xw1X3qkkYqSP3d46vBhbgAS2rDg/pub?output=csv", 
            {
                responseType: "blob"
            }
        )
         Papa.parse(response.data, 
            {
                header: true,
                complete: function(results) {
                    console.log(results.data);
                    products = results.data;
                }
            }
        )
    });
</script>

<h1
    class="text-4xl font-semibold text-center text-blue-600 p-16"
>
   Pasteles Jonhy
</h1>

<div class="max-w-[1200px] mx-auto gap-12 flex flex-wrap justify-center">
    {#each products as {name, price, image}}
        <div class="flex-col items-center shadow-md rounded-md overflow-hidden w-[300px]">
            <img  src={image} class="w-full h-48 object-cover " alt={name} />
            <h2 class="text-2xl p-6 font-semibold text-center text-gray-600">{name}</h2>
            <p class="text-2xl  p-6 font-semibold text-center text-gray-600">{price}</p>
        </div>
    {/each}
</div>



