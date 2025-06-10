<script lang="ts">
  import Cloud from "$lib/components/Cloud.svelte";
</script>

<div class="banner">
  <!-- <Cloud /> -->
  <img src="/clouds/moon.png" alt="moon" class="moon" />
  <div class="content">
    <h2>Dinael Aragon</h2>
    <p>This site is under construction</p>
  </div>
</div>

<style>
  .banner {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100vw;
    height: 100svh;
    overflow-x: hidden;
    position: relative;
  }

  .banner::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image: url("/bgimage.jpg");
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
    z-index: -2;
    mask-image: url("/mask.gif");
    mask-size: cover;
    mask-position: center;
    filter: hue-rotate(10deg) saturate(1);
  }
  .banner::after {
    content: "";
    position: absolute;
    inset: 0;
    background-color: var(--bg-primary);
    opacity: 0.5;
    z-index: -1;
  }
  .moon {
    position: fixed;
    top: 100px;
    right: 200px;
    width: 100px;
    height: 100px;
    z-index: -1;
    filter: drop-shadow(0 0 1.5rem #c8e0ff) drop-shadow(0 0 0.2rem #c8e0ff);
  }
  h2 {
    font-size: 2.5rem;
  }
  p {
    font-size: 1.5rem;
  }
</style>
