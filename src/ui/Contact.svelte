<script>
	import QR from './QR.svelte';
	import WS from './WS.svelte';

	const PHONE = '56963313784';
</script>

<div class="h-screen bg-red-100 w-full pt-20 gap-36 flex flex-col">
	<span>
		<h1 class="text-4xl font-semibold text-center ">¿Quieres consultar por algun producto?</h1>
		<p class="text-2xl text-center text-gray-600 pt-6">Envianos un mensaje por WhatsApp</p>
	</span>

	<div class="flex flex-col justify-center items-center gap-6">
		<QR className="fill-red-100" />

		<a
			class="flex justify-center items-center gap-1 text-lg font-semibold"
			href="https://wa.me/{PHONE}?text=Hola,%20me%20gustaría%20saber%20más%20sobre%20los%20productos%20de%20pasteleria%20que%20ofrecen."
			title="WhatsApp"
			target="_blank"
			rel="noopener noreferrer"
		>
			<WS />
			+{PHONE}
		</a>
	</div>
</div>
