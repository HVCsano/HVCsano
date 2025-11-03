<script>
	import { onMount } from 'svelte';

	onMount(() => {
		document.getElementById('generate')?.addEventListener('submit', (ev) => {
			ev.preventDefault();
			loadMap();
		});
		function loadMap() {
			let mapEl = document.getElementById('map');
			let size = document.getElementById('size');
			mapEl.innerHTML = '';
			let layout = [12, 12, 12, 12, 12, 12, 12, 12, 12, 12, 12, 12];
			for (let i = 0; i < layout.length; i++) {
				let rowDiv = document.createElement('div');
				rowDiv.style = 'display: flex;';
				mapEl.appendChild(rowDiv);
				for (let j = 1 + i * 12; j < layout[i] * (i + 1) + 1; j++) {
					let img = document.createElement('img');
					img.setAttribute('src', `/map/${j}.png`);
					img.setAttribute('width', `${size.value}px`);
					img.setAttribute('height', `${size.value}px`);
					img.setAttribute('onerror', "this.style.opacity='0'");
					rowDiv.appendChild(img);
					console.log(j);
				}
			}
		}
	});
</script>

<form id="generate" class="text-white">
	<label for="size">Mapméret:</label>
	<input
		type="number"
		class="border-2 border-amber-500 text-white"
		max="512"
		min="1"
		name="size"
		placeholder="256"
		id="size"
	/>
	<button type="submit" class="cursor-pointer bg-amber-600">Generálás</button>
	<h2>Oldalt készítette: HVCsano, a képek a SeeMTA v4 modjából kiszedve.</h2>
</form>

<div id="map"></div>

<span class="fixed top-0 left-0 -z-20 h-[100%] w-[100%] bg-gray-700"></span>
