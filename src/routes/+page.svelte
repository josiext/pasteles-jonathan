<script lang="ts">
	import { onMount } from 'svelte';
	import axios from 'axios';
	import Papa from 'papaparse';
	import Contact from '../ui/Contact.svelte';
	import Catalog from '../ui/Catalog.svelte';
	import Home from '../ui/Home.svelte';

	const DOC_LINK =
		'https://docs.google.com/spreadsheets/d/e/2PACX-1vSlTuh4wcDhnwmHdgzkyD1rNI_HeCy2Hhha5gu237IxiYB7MQEb4xw1X3qkkYqSP3d46vBhbgAS2rDg/pub?output=csv';

	let products: { name: string; price: number; image: string }[] = [];

	onMount(async () => {
		const response = await axios.get(DOC_LINK, {
			responseType: 'blob'
		});
		Papa.parse(response.data, {
			header: true,
			complete: function (results) {
				products = results.data as any;
			}
		});
	});
</script>

<Home />

<Catalog {products} />

<Contact />
