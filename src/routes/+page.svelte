<script lang="ts">
  import Query from "./Query.svelte";
  import Confetti from "./Confetti.svelte";
	import Confirmation from "./Confirmation.svelte";

  let clickedYes = $state(false);

  function yesClicked() {
    clickedYes = true;
  }
</script>

{#if !clickedYes}
  <Query {yesClicked} />
{:else}
  <Confetti />
  <Confirmation />
{/if}
