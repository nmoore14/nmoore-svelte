<script>
  import { x_value, y_value, x_css, y_css } from '../store.js';

  export let segment;
  
</script>

<style>
  .background {
    z-index: -100;
  }

  h1 {
    font-size: 20rem;
    font-weight: bolder;
    color: #EDF2F7;
  }
</style>

<div class="fixed flex flex-col w-screen h-screen items-center content-center justify-center bg-gray-200 background">
  <h1 style="text-shadow: -{$x_css}px -{$y_css}px 10px #FBFCFD, {$x_css}px {$y_css}px 10px #D5D9DE;">.dev</h1>
  <h2 class="text-gray-300">
    X: {$x_value} | Y: {$y_value}
  </h2>
  <h2 class="text-gray-300">
    (Mouse position in window)
  </h2>
    <h2 class="text-gray-300">
    X: {$x_css} | Y: {$y_css}
  </h2>
</div>