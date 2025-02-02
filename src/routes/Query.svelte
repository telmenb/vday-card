<script lang="ts">
  import { fly } from 'svelte/transition';
	import jumpBear from '$lib/jump-bear.gif';

  let { setClickedYes } = $props();
  let clickedNo = $state(false);
  let showHuh = $state(false);

  async function noClicked() {
    console.log('no clicked');
    await new Promise(resolve => resolve(showHuh = false));
    clickedNo = true;
  }
</script>

<h1 class="text-4xl font-semibold font-serif">Cecylia!</h1>
<p class="mt-3 font-serif text-xl">Will you be my Valentine?</p>

<img
  src={jumpBear}
  alt="Mocha Bear Jumping with Hearts"
  width="200"
  height="200"
/>

<div class ="flex mt-2">
  <button
    class="mx-2 px-4 py-2 bg-pink-500 text-white rounded-md"
    onclick={() => setClickedYes(true)}
  >
    Yes
  </button>
  {#if !clickedNo}
    <div class="flex">
      <button
      onmouseenter={() => showHuh = true}
      onmouseleave={() => showHuh = false}
      onclick={noClicked}
      out:fly={{ x: 700, duration: 500 }}
      class="mx-2 px-4 py-2 bg-pink-500 text-white rounded-md"
      >
      No
    </button>
    {#if showHuh}
    <p id="emoji">🤨</p>
    {/if}
  </div>
  {/if}
</div>

<style>
  #emoji {
    position: fixed;
    top: 50%;
    left: 50%;
    font-size: 150px;
    transform: translate(-50%, -50%);
  }
</style>
