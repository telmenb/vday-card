<script lang="ts">
  import Query from "./Query.svelte";
  import Confetti from "./Confetti.svelte";
	import Confirmation from "./Confirmation.svelte";

  let clickedYes = $state(false);

  function setClickedYes(bool: boolean) {
    clickedYes = bool;
  }
</script>

{#if !clickedYes}
  <Query {setClickedYes} />
{:else}
  <Confetti />
  <Confirmation {setClickedYes} />
{/if}
