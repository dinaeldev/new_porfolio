<script lang="ts">
</script>

<header>
  <div class="logotipo">
    <img src="/logo/daragon_isotipo.png" alt="" width="150px" height="150px" />
    <div class="text">
      <span class="name">Dinael Aragón</span>
      <span class="title">Software Engineer</span>
    </div>
  </div>
</header>

<style>
  header {
    width: 100%;
    height: 100px;
    position: fixed;
    top: 0;
    inset: 0;
  }
  .logotipo {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 250px;
  }
  .logotipo img {
    width: 100px;
    height: 100px;
    transform: rotateY(180deg);
  }
  .logotipo .text{
    display: flex;
    flex-direction: column;
  }
  .logotipo .text .name {
    font-size: 1.6rem;
    line-height: 1;
    text-shadow: 0 0 10px var(--accent-pink);
  }
  .logotipo .text .title {
    font-size: 0.8rem;
    text-wrap: nowrap;
    text-shadow: 0 0 10px var(--accent-pink);
  }
</style>
