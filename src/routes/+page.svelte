<script lang="ts">
	import { browser } from '$app/environment';
	import Query from './Query.svelte';
	import Confetti from './Confetti.svelte';
	import Confirmation from './Confirmation.svelte';

	let clickedYes = $state(initClickedYes());

	function initClickedYes() {
		let result = false;
		if (browser) {
			result = JSON.parse(window.localStorage.getItem('clickedYes') ?? 'false');
		}
		return result;
	}

	function setClickedYes(bool: boolean) {
		clickedYes = bool;
		if (browser) {
			window.localStorage.setItem('clickedYes', bool.toString());
		}
	}

	$inspect(clickedYes);
</script>

{#if !clickedYes}
	<Query {setClickedYes} />
{:else}
	<Confetti />
	<Confirmation {setClickedYes} />
{/if}
