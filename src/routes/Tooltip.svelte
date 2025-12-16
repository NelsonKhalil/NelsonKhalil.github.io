<script>
  import { globalState } from './globalState.svelte.js';

  let { mouseX, mouseY } = $state({ mouseX: 0, mouseY: 0 });

  function mouseMove(event) {
    mouseX = event.clientX;
    mouseY = event.clientY;
  }

</script>

<svelte:window onmousemove={mouseMove} />

{#if (globalState.tooltipText != "")}
  <i class="fi fi-rr-search fixed z-60 pointer-events-none scale-200" style="left: {mouseX - 5}px; top: {mouseY - 2}px;"></i>
  <div class="fixed z-60 pointer-events-none p-2 backdrop-blur-[5px] rounded border-3 shadow-2xl border-gray-500" style="left: {mouseX + 30}px; top: {mouseY - 15}px;">
    {@html globalState.tooltipText}
  </div>

  <style>
    * {
      cursor: none;
    }
  </style>
{/if}