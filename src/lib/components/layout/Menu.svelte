<script lang="ts">
  let { isOpen = $bindable() } = $props();
</script>

<nav class="menu" class:active={isOpen}>
  <div class="links">
    <a href="/">About Us</a>
    <a href="/portafolio">Projects</a>
    <a href="/">Contact Me</a>
  </div>
</nav>

<style>
  nav {
    background-color: var(--orange);
    width: 0;
    height: 100%;
    position: fixed;
    top: 0;
    right: 0;
    transition: all 500ms ease;
    z-index: 3;
    overflow: hidden;
  }
  nav::after {
    content: "";
    width: 0;
    height: 100%;
    background-color: var(--blue);
    transition: all 500ms ease;
    transition-delay: 200ms;
    position: fixed;
    top: 0;
    right: 0;
    z-index: 1;
    pointer-events: none;
  }
  nav.active::after,
  nav.active {
    width: 100%;
  }
  .links {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 100%;
    height: 100%;
    position: relative;
    z-index: 2;
    opacity: 0;
    transform: scaleX(0);
    transform-origin: right;
    transition: all 500ms ease;
    transition-delay: 250ms;
    overflow: hidden;
  }
  nav.active .links{
    opacity: 1;
    transform: scaleX(1);
  }
  .links a {
    font-family: var(--title);
    font-size: clamp(3rem, 5vw, 4rem);
    letter-spacing: 5px;
    cursor: pointer;
    transition: all 200ms ease;
    position: relative;
    padding: 10px 0;
    display: block;
    width: 90vw;
    max-width: 450px;
  }
  .links a:hover{
    color: var(--white);
  }
  .links a::before{
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 4px;
    border-radius: 20px;
    background-color: var(--white);
    transition: all 350ms ease;
  }
  .links a:hover::before{
    width: 120%;
  }
</style>
