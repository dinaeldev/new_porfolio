<script lang="ts">
  import Cloud from "$lib/components/Cloud.svelte";
</script>

<div class="banner">
  <!-- <Cloud /> -->
  <img src="/clouds/moon.png" alt="moon" class="moon" />
  <div class="content">
    <div class="slogan">
      <h2>Dinael Aragon</h2>
      <p>Software & Web Developer</p>
    </div>
  </div>
</div>

<style>
  .banner {
    width: 100%;
    height: 100svh;
    overflow-x: hidden;
    position: relative;
  }
  .banner::after {
    content: "";
    position: absolute;
    inset: 0;
    background-image: url("/edificios.png");
    background-size: cover;
    background-position: bottom;
    opacity: 1;
    z-index: -1;
    mask-image: url("/mask.gif");
    mask-size: cover;
    mask-position: center;
    filter: drop-shadow(0 0 10px #1d2133) hue-rotate(20deg);
    opacity: 0.8;
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
    filter: hue-rotate(10deg) saturate(1);
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
  .slogan {
    width: 95%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    animation: slogan 3s ease forwards;
    transition: all 500ms cubic-bezier(0.075, 0.82, 0.165, 1);
    animation-delay: 1s;
  }
  .slogan h2 {
    font-size: 2.5rem;
  }
  .slogan p {
    font-size: 1.5rem;
  }
  @keyframes slogan {
    from {
      top: 50%;
      left: 50%;
    }
    to {
      top: 30%;
    }
  }
</style>
