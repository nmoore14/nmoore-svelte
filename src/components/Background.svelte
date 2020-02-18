<script>
  import { onMount } from 'svelte';
  import { x_value, y_value, x_css, y_css, rev_x_css, rev_y_css } from '../store.js';

  export let segment;

  $: w = isMobile(w);
  $: mobile = w;
  
  function isMobile(win) {
    let win_width;

    if(win <= 1024) {
      win_width = true;
    } else {
      win_width = false;
    }
    
    return win_width;
  }

  onMount(() => {
    isMobile(w);
  })

</script>

<style>
  .background {
    z-index: -100;
  }

  h1 {
    font-weight: bolder;
    color: #EDF2F7;
  }
</style>

<svelte:window bind:innerWidth={w} on:resize={isMobile}/>

<div class="fixed flex flex-col w-screen h-screen items-center content-center justify-center bg-gray-200 background" id="background-container">
  {#if !segment && !mobile}
    <h1 
      class="font-bolder text-mob md:text-desk"
      style="text-shadow: -{$x_css}px -{$y_css}px 10px #FBFCFD, {$x_css}px {$y_css}px 10px #D5D9DE;"
    >
      .dev
    </h1>
  {:else}
    <h1 
      class="font-bolder text-mob md:text-desk"
      style="text-shadow: -2px -2px 10px #FBFCFD, 2px 2px 10px #D5D9DE;"
    >
      .dev
    </h1>
  {/if}
  <h2 class="text-gray-300">
    X: {$x_value} | Y: {$y_value}
  </h2>
  <h2 class="text-gray-300">
    (Mouse position in window)
  </h2>
</div>