<h1>Temperature Converter</h1>

<p>This is a simple Temperature Converter made with SvelteKit, TypeScript, and SCSS</p>

<div class="converter">
	<div class="units">
		<div class="unit">
			<h2>Celsius</h2>
			<div class="row">
				<input type="number" />
				<p>°C</p>
			</div>
		</div>
		<div class="unit">
			<h2>Fahrenheit</h2>
			<div class="row">
				<input type="number" />
				<p>°F</p>
			</div>
		</div>
	</div>
	<div class="convert-button">
		<button>Convert</button>
	</div>
</div>

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
