<script>
	let minIntensity = 4;
	let maxIntensity = 7;
</script>

<div class="flex flex-col gap-4 justify-between w-64 mb-10">
	<label for="" class="flex justify-between">
		min-Intensity
		<input type="number" class="border" bind:value={minIntensity} />
	</label>

	<label for="" class="flex justify-between">
		max-Intensity
		<input type="number" class="border" bind:value={maxIntensity} />
	</label>
</div>
<div class="w-96">
	<div class="mb-2 font-sans font-bold">INTENSITY LEVEL</div>
	<div
		style="background:linear-gradient(90deg, #52ff52, #fb5c5c);
        --minIntensity:{minIntensity};
        --maxIntensity:{maxIntensity}"
		class="h-14 text-white flex justify-evenly items-end relative intensity
    "
	>
		<div class="border-t-2 border-white w-full flex justify-evenly pt-2">
			<div class="scale relative">1</div>
			<div class="scale relative">2</div>
			<div class="scale relative">3</div>
			<div class="scale relative min-intensity">4</div>
			<div class="scale relative">5</div>
			<div class="scale relative">6</div>
			<div class="scale relative max-intensity">7</div>
			<div class="scale relative">8</div>
			<div class="scale relative">9</div>
			<div class="scale relative">10</div>
		</div>
	</div>
</div>

<style>
	.scale::after {
		content: '';
		position: absolute;
		top: 0;
		left: 0;
		width: 2px;
		/* height: calc(100% - 2px); */
		height: 10px;
		background: white;
		transform: translate(150%, -140%);
		transform-origin: right;
	}
	.intensity::before {
		content: '';
		position: absolute;
		top: 0;
		left: 0;
		border: 2px solid black;
		/* width: calc(var(--maxIntensity) * 2.5rem - var(--minIntensity) * 2.5rem); */
		width: calc(2.2rem * (var(--maxIntensity) - var(--minIntensity) + 1));
		height: 4rem;
		transform: translate(calc(-1.5rem + var(--minIntensity) * 2.2rem), -0.4rem);
	}
</style>
