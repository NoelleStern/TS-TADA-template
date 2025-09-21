<script lang="ts">
</script>


<!-- I've put all of the cool stuff in here to not litter up the app.css -->
<style>
  :global(:root) {
    --icon-scale: 10;
    --bloom-color: #9d960875;
    --flicker-color1: #ea36af;
    --flicker-color2: #75fa69;
  }

  :global(html) { 
    text-shadow: 0.06rem 0 0.06rem var(--flicker-color1), -0.125rem 0 0.06rem var(--flicker-color2);
    animation: 0.01s linear 0s infinite alternate running text-flicker;
  }

  .main-container {
    height: 100vh;
    background: radial-gradient(#140052, black);
  }

  .crt {
    z-index: 1;
    background: linear-gradient(to top, transparent, transparent, black, black);
    background-size: 100% 4px;
    opacity: 0.3;
  }

  .icon {
    image-rendering: pixelated;
    height: calc(21px * var(--icon-scale));
    filter: drop-shadow(0 0 2rem var(--bloom-color));
    animation: 1s ease-in 0s infinite alternate running bloom-flicker;
  }

  @keyframes -global-text-flicker {
    from { text-shadow: 1px 0 0 var(--flicker-color1), -2px 0 0 var(--flicker-color2); }
    to { text-shadow: 0px 0.5px 0px var(--flicker-color1), -1px -0.5px 2px var(--flicker-color2); }
  }

  @keyframes -global-bloom-flicker {
    from { filter: drop-shadow(0 0 2rem var(--bloom-color)); }
    to { filter: drop-shadow(0 0 4rem var(--bloom-color)); }
  }
</style>


<main class="main-container">

  <!-- CRT overlay -->
  <div class="absolute size-full crt"></div>
  
  <!-- Main container -->
  <div class="flex flex-col justify-center items-center gap-9 size-full">
    <img class="icon" alt="WAH!" src="/NoelleIcon2000.gif">
    <!-- <div class="text-gray-300 text-6xl">Hello, world!</div> -->
    <div class="indicator">
      <span class="indicator-item badge badge-primary">WAH!</span>
      <div class="alert flex flex-col gap-1">
        <span class="text-2xl">TS-TADA:</span>
        <span class="text-lg">Typescript + Svelte + TAilwind + DAisy ui ✨</span>
      </div>
    </div>
  </div>

</main>