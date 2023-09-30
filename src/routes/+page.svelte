<script lang="ts">
	import { onMount } from 'svelte';

	let celsiusElement: HTMLInputElement;
	let fahrenheitElement: HTMLInputElement;
	let display: string;

	function handleEvent(event: { key: string }) {
		if (event.key === 'Enter') {
			convertToFahrenheit();
		}
	}

	onMount(() => {
		celsiusElement = document.getElementById('celsius') as HTMLInputElement;
		fahrenheitElement = document.getElementById('fahrenheit') as HTMLInputElement;

		document.addEventListener('keydown', handleEvent);
	});

	function convertToFahrenheit() {
		if (celsiusElement && fahrenheitElement) {
			const celsiusInput = parseFloat(celsiusElement.value);

			if (!isNaN(celsiusInput)) {
				let fahrenheitOutput = (celsiusInput * 9) / 5 + 32;
				fahrenheitOutput = parseFloat(fahrenheitOutput.toFixed(2));
				fahrenheitElement.value = fahrenheitOutput.toString();
			} else {
				display = 'Invalid input. Please enter a valid number for Celsius.';

				setTimeout(() => {
					display = '';
				}, 2000);
				celsiusElement.value = '';
				fahrenheitElement.value = '';
			}
		}
	}
</script>

<h1>Temperature Converter</h1>

<p>This is a simple Temperature Converter made with SvelteKit, TypeScript, and SCSS</p>

<div class="converter">
	<div class="units">
		<div class="unit">
			<h2>Celsius</h2>
			<div class="row">
				<input type="number" id="celsius" />
				<p>°C</p>
			</div>
		</div>
		<div class="unit">
			<div class="row">
				<p>-></p>
			</div>
		</div>
		<div class="unit">
			<h2>Fahrenheit</h2>
			<div class="row">
				<input type="number" id="fahrenheit" />
				<p>°F</p>
			</div>
		</div>
	</div>
	<div class="convert-button">
		<button on:click={convertToFahrenheit}>Convert</button>
	</div>
</div>

{#if display}
	<div style="margin-top: 1rem;">
		<p class="error">{display}</p>
	</div>
{/if}

<style lang="scss">
	.row {
		input[type='number'] {
			width: 10rem;

			&::-webkit-inner-spin-button,
			&::-webkit-outer-spin-button,
			&::-moz-outer-spin-button,
			&::-moz-inner-spin-button {
				-webkit-appearance: none;
				appearance: none;
				margin: 0;
			}
		}

		p {
			margin-left: 1rem;
		}

		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.units {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
	}

	.converter {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.unit {
		margin: 0 1rem;
	}

	.convert-button {
		margin-top: 1rem;
	}
</style>
