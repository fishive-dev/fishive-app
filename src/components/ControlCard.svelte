<script>
	let pizeoState = 'on';
  let pumpState = 'on';

	let r = 255;
	let g = 255;
	let b = 255;
	let a = 255;

	async function doRGBToggle() {

		var requestOptions = {
			method: 'GET',
			redirect: 'follow',
      Headers: {
        'Access-Control-Allow-Origin': 'https://devnode.fishive.site/'
      }

		};

		fetch('http://devnode.fishive.site/rgb-state?state=on&r=' + r + '&g=' + g + '&b=' + b + '&brightness=' + a)
			.then((response) => response.text())
			.then((result) => console.log(result))
			.catch((error) => console.log('error', error));
	}

	async function doPizeoToggle() {
		if (pizeoState == 'on') {
			pizeoState = 'off';
		} else {
      pizeoState = 'on';
    }

		var requestOptions = {
			method: 'GET',
			redirect: 'follow',
      Headers: {
        'Access-Control-Allow-Origin': 'https://devnode.fishive.site/'
      }

		};

		fetch('https://devnode.fishive.site/pizeo-state?state=' + pizeoState, requestOptions)
			.then((response) => response.text())
			.then((result) => console.log(result))
			.catch((error) => console.log('error', error));
	}

  async function doPumpToggle() {
		if (pumpState == 'on') {
			pumpState = 'off';
		} else {
      pumpState = 'on';
    }

		var requestOptions = {
			method: 'GET',
			redirect: 'follow',
      Headers: {
        'Access-Control-Allow-Origin': 'https://devnode.fishive.site/'
      }

		};

		fetch('https://devnode.fishive.site/pump-state?state=' + pumpState, requestOptions)
			.then((response) => response.text())
			.then((result) => console.log(result))
			.catch((error) => console.log('error', error));
	}
</script>

<div class="shadow-md text-center max-w-sm rounded-md m-5 bg-white">
	<span class="text-lg font-extrabold">Control the Tank</span>

	<div class="grid grid-cols-1 gap-3 p-5">
		<button on:click={doPizeoToggle} class="btn btn-outline btn-info">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
				<path
					d="M5.85 3.5a.75.75 0 00-1.117-1 9.719 9.719 0 00-2.348 4.876.75.75 0 001.479.248A8.219 8.219 0 015.85 3.5zM19.267 2.5a.75.75 0 10-1.118 1 8.22 8.22 0 011.987 4.124.75.75 0 001.48-.248A9.72 9.72 0 0019.266 2.5z"
				/>
				<path
					fill-rule="evenodd"
					d="M12 2.25A6.75 6.75 0 005.25 9v.75a8.217 8.217 0 01-2.119 5.52.75.75 0 00.298 1.206c1.544.57 3.16.99 4.831 1.243a3.75 3.75 0 107.48 0 24.583 24.583 0 004.83-1.244.75.75 0 00.298-1.205 8.217 8.217 0 01-2.118-5.52V9A6.75 6.75 0 0012 2.25zM9.75 18c0-.034 0-.067.002-.1a25.05 25.05 0 004.496 0l.002.1a2.25 2.25 0 11-4.5 0z"
					clip-rule="evenodd"
				/>
			</svg>
			<span class="pl-2">Trigger Alarm</span>
		</button>

		<button on:click={doPumpToggle} class="btn btn-outline btn-success">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
				<path
					d="M21 6.375c0 2.692-4.03 4.875-9 4.875S3 9.067 3 6.375 7.03 1.5 12 1.5s9 2.183 9 4.875z"
				/>
				<path
					d="M12 12.75c2.685 0 5.19-.586 7.078-1.609a8.283 8.283 0 001.897-1.384c.016.121.025.244.025.368C21 12.817 16.97 15 12 15s-9-2.183-9-4.875c0-.124.009-.247.025-.368a8.285 8.285 0 001.897 1.384C6.809 12.164 9.315 12.75 12 12.75z"
				/>
				<path
					d="M12 16.5c2.685 0 5.19-.586 7.078-1.609a8.282 8.282 0 001.897-1.384c.016.121.025.244.025.368 0 2.692-4.03 4.875-9 4.875s-9-2.183-9-4.875c0-.124.009-.247.025-.368a8.284 8.284 0 001.897 1.384C6.809 15.914 9.315 16.5 12 16.5z"
				/>
				<path
					d="M12 20.25c2.685 0 5.19-.586 7.078-1.609a8.282 8.282 0 001.897-1.384c.016.121.025.244.025.368 0 2.692-4.03 4.875-9 4.875s-9-2.183-9-4.875c0-.124.009-.247.025-.368a8.284 8.284 0 001.897 1.384C6.809 19.664 9.315 20.25 12 20.25z"
				/>
			</svg>

			<span class="pl-2">Toggle Pump</span>
		</button>

		<button class="btn btn-outline btn-warning">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
				<path
					fill-rule="evenodd"
					d="M19.449 8.448L16.388 11a4.52 4.52 0 010 2.002l3.061 2.55a8.275 8.275 0 000-7.103zM15.552 19.45L13 16.388a4.52 4.52 0 01-2.002 0l-2.55 3.061a8.275 8.275 0 007.103 0zM4.55 15.552L7.612 13a4.52 4.52 0 010-2.002L4.551 8.45a8.275 8.275 0 000 7.103zM8.448 4.55L11 7.612a4.52 4.52 0 012.002 0l2.55-3.061a8.275 8.275 0 00-7.103 0zm8.657-.86a9.776 9.776 0 011.79 1.415 9.776 9.776 0 011.414 1.788 9.764 9.764 0 010 10.211 9.777 9.777 0 01-1.415 1.79 9.777 9.777 0 01-1.788 1.414 9.764 9.764 0 01-10.212 0 9.776 9.776 0 01-1.788-1.415 9.776 9.776 0 01-1.415-1.788 9.764 9.764 0 010-10.212 9.774 9.774 0 011.415-1.788A9.774 9.774 0 016.894 3.69a9.764 9.764 0 0110.211 0zM14.121 9.88a2.985 2.985 0 00-1.11-.704 3.015 3.015 0 00-2.022 0 2.985 2.985 0 00-1.11.704c-.326.325-.56.705-.704 1.11a3.015 3.015 0 000 2.022c.144.405.378.785.704 1.11.325.326.705.56 1.11.704.652.233 1.37.233 2.022 0a2.985 2.985 0 001.11-.704c.326-.325.56-.705.704-1.11a3.016 3.016 0 000-2.022 2.985 2.985 0 00-.704-1.11z"
					clip-rule="evenodd"
				/>
			</svg>
			<span class="pl-2">Feed Now</span>
		</button>
		<div class="flex">
			<input type="text" bind:value={r} placeholder="R" class="input input-bordered w-full max-w-xs" />
			<input type="text" bind:value={g} placeholder="G" class="input input-bordered w-full max-w-xs ml-2" />
			<input type="text" bind:value={b} placeholder="B" class="input input-bordered w-full max-w-xs ml-2" />
			<input type="text" bind:value={a} placeholder="A" class="input input-bordered w-full max-w-xs ml-2" />
			<button class="btn btn-square btn-primary ml-2" on:click={doRGBToggle}>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					viewBox="0 0 24 24"
					fill="currentColor"
					class="w-6 h-6"
				>
					<path
						d="M9.97.97a.75.75 0 011.06 0l3 3a.75.75 0 01-1.06 1.06l-1.72-1.72v3.44h-1.5V3.31L8.03 5.03a.75.75 0 01-1.06-1.06l3-3zM9.75 6.75v6a.75.75 0 001.5 0v-6h3a3 3 0 013 3v7.5a3 3 0 01-3 3h-7.5a3 3 0 01-3-3v-7.5a3 3 0 013-3h3z"
					/>
					<path
						d="M7.151 21.75a2.999 2.999 0 002.599 1.5h7.5a3 3 0 003-3v-7.5c0-1.11-.603-2.08-1.5-2.599v7.099a4.5 4.5 0 01-4.5 4.5H7.151z"
					/>
				</svg>
			</button>
		</div>
		<button class="btn btn-outline btn-error">REBOOT</button>
	</div>
</div>
