<script>
	import { goto } from '$app/navigation';
	import { WEBUI_NAME, config } from '$lib/stores';
	import {
		WEBUI_BACKEND_URL_STORAGE_KEY,
		WEBUI_BASE_URL,
		normalizeWebUIBaseUrl
	} from '$lib/constants';
	import { onMount, getContext } from 'svelte';

	const i18n = getContext('i18n');

	let loaded = false;
	let backendUrl = WEBUI_BASE_URL || 'http://127.0.0.1:8080';
	let backendUrlError = '';

	const saveBackendUrl = async () => {
		const normalized = normalizeWebUIBaseUrl(backendUrl);
		if (!normalized) {
			backendUrlError = 'Backend URL is required.';
			return;
		}

		localStorage.setItem(WEBUI_BACKEND_URL_STORAGE_KEY, normalized);
		backendUrlError = '';
		location.href = '/';
	};

	onMount(async () => {
		if ($config) {
			await goto('/');
		}

		loaded = true;
	});
</script>

{#if loaded}
	<div class="absolute w-full h-full flex z-50">
		<div class="absolute rounded-xl w-full h-full backdrop-blur-sm flex justify-center">
			<div class="m-auto pb-44 flex flex-col justify-center">
				<div class="max-w-md">
					<div class="text-center text-2xl font-medium z-50">
						{$i18n.t('{{webUIName}} Backend Required', { webUIName: $WEBUI_NAME })}
					</div>

					<div class=" mt-4 text-center text-sm w-full">
						{$i18n.t('Unable to reach backend with the current URL.')}
						<br class=" " />
						{$i18n.t('Set the backend URL below and try again.')}
					</div>

					<div class="mt-5">
						<label class="text-sm font-medium" for="backend-url">{$i18n.t('Backend URL')}</label>
						<input
							id="backend-url"
							type="text"
							class="mt-2 w-full rounded-md border border-gray-300 bg-white px-3 py-2 text-sm text-black"
							placeholder="http://127.0.0.1:8080"
							bind:value={backendUrl}
						/>

						{#if backendUrlError}
							<div class="mt-2 text-xs text-red-600">{backendUrlError}</div>
						{/if}
					</div>

					<div class=" mt-6 mx-auto relative group w-fit flex gap-2">
						<button
							class="relative z-20 flex px-5 py-2 rounded-full bg-gray-900 hover:bg-black transition font-medium text-sm text-white"
							on:click={saveBackendUrl}
						>
							{$i18n.t('Save and Retry')}
						</button>

						<button
							class="relative z-20 flex px-5 py-2 rounded-full bg-gray-100 hover:bg-gray-200 transition font-medium text-sm text-black"
							on:click={() => {
								location.href = '/';
							}}
						>
							{$i18n.t('Check Again')}
						</button>
					</div>
				</div>
			</div>
		</div>
	</div>
{/if}
