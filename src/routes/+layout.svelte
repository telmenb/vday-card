<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<div class="h-screen flex flex-col items-center justify-center bg-pink-100">
	{@render children()}
</div>
