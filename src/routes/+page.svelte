<script lang="ts">
  import Cloud from "$lib/components/Cloud.svelte";
</script>

<div class="banner">
  <!-- <Cloud /> -->
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
