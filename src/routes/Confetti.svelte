<script lang="ts">
	import { confetti } from '@neoconfetti/svelte';
</script>

<div
	style="position: absolute; left: 50%; top: 30%"
	use:confetti={{
		particleCount: 400,
		force: 0.8,
		stageWidth: window.innerWidth,
		stageHeight: window.innerHeight,
		colors: ['#FFCCCB', '#FC8EAC', '#FF007F']
	}}
></div>
