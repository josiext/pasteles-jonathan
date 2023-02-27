<script>
	import QR from './QR.svelte';
	import WS from './WS.svelte';

	const PHONE = '963313784';
</script>

<div id="contact" class="h-screen bg-red-100 w-full pt-20 gap-36 flex flex-col">
	<span>
		<h1 class="text-4xl font-semibold text-center text-red-700">
			¿Quieres consultar por algun producto?
		</h1>
		<p class="text-2xl text-center text-gray-600 pt-6 text-red-700">
			Envianos un mensaje por WhatsApp
		</p>
	</span>

	<div class="flex flex-col justify-center items-center gap-6">
		<QR className="fill-red-200 rounded-lg" />

		<span class="bg-red-200 py-1 px-4 rounded-md hover:bg-red-300">
			<a
				class="flex justify-center items-center gap-1 text-lg text-[#C32828] font-semibold"
				href="https://wa.me/56{PHONE}?text=Hola,%20me%20gustaría%20saber%20más%20sobre%20los%20productos%20de%20pasteleria%20que%20ofrecen."
				title="WhatsApp"
				target="_blank"
				rel="noopener noreferrer"
			>
				<WS />
				+56 {PHONE}
			</a>
		</span>
	</div>
</div>
