<script  lang="ts">
  import { onMount } from "svelte";

  let scrollY = 0;

  onMount(() => {
    const updateScroll = () => {
      scrollY = window.scrollY;
    };
    window.addEventListener("scroll", updateScroll);
    return () => window.removeEventListener("scroll", updateScroll);
  });

  const clouds = [
    { src: "/clouds/1.png", top: 100, left: 50, speed: 0.3 },
    { src: "/clouds/2.png", top: 200, left: 200, speed: 0.6 },
    { src: "/clouds/3.png", top: 300, left: 100, speed: 0.9 },
    { src: "/clouds/4.png", top: 400, left: 500, speed: 1.2 },
  ];
</script>

<div class="cloud-layer">
  {#each clouds as cloud}
    <img
      class="cloud"
      src={cloud.src}
      alt="cloud"
      style="
        top: {cloud.top}px;
        left: {cloud.left}px;
        transform: translateY({-scrollY * cloud.speed}px);
      "
    />
  {/each}
</div>

<style>
  .cloud-layer {
    position: absolute;
    width: 100%;
    height: 100vh;
    pointer-events: none;
    overflow: hidden;
    z-index: -1;
  }

  .cloud {
    position: absolute;
    will-change: transform;
    transition: transform 0.1s linear;
    width: 250px;
  }
</style>
