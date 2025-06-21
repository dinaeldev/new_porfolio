<script lang="ts">
  import Menu from "./Menu.svelte";
</script>

<header>
  <div class="logotipo">
    <img src="/logo/daragon_isotipo.png" alt="" width="150px" height="150px" />
    <div class="text">
      <p class="name">Dinael Aragón</p>
      <span class="title">Software & Web Developer</span>
    </div>
  </div>
  <Menu />
</header>

<style>
  header {
    width: 100%;
    height: 100px;
    max-width: 1480px;
    margin: 0 auto;
    position: fixed;
    top: 0;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: space-between;
    z-index: 999;
  }
  .logotipo {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    max-width: 400px;
  }
  .logotipo img {
    width: 100px;
    height: 100px;
    transform: rotateY(180deg);
  }
  .logotipo .text .name {
    font-size: clamp(1.4rem, 1.4vw, 2rem);
    line-height: 1;
    text-shadow: 0 0 10px var(--accent-pink);
  }
  .logotipo .text .title {
    font-size: clamp(1rem, 1vw, 1.6rem);
    text-wrap: nowrap;
    text-shadow: 0 0 10px var(--accent-pink);
    letter-spacing: 0.5px;
  }
</style>
