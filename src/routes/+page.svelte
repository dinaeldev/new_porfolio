<div class="banner">
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
    height: 100svh;
    position: relative;
  }

  .banner::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image: url("/igris_.jpg");
    background-size: cover;
    background-position: center;
    filter: blur(1.5px) hue-rotate(10deg) saturate(2);
    z-index: -2;
    mask-image: url("/mask.gif");
    mask-size: cover;
    mask-position: center;
  }
  .banner::after {
    content: "";
    position: absolute;
    inset: 0;
    background-color: var(--bg-primary);
    opacity: 0.6;
    z-index: -1;
  }
  h2 {
    font-size: 2.5rem;
  }
  p {
    font-size: 1.5rem;
  }
</style>
