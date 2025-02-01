<script lang='ts'>
  import Query from "./Query.svelte";

  let clickedYes = $state(false);

  function yesClicked() {
    clickedYes = true;
  }
</script>

{#if !clickedYes}
  <Query {yesClicked} />
{:else}
  <p>let's goo!</p>
{/if}