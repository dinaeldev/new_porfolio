<script lang="ts">
  import { bodyScroll } from "$lib/utils/bodyScroll";

  let isOpen = $state(false);

  $effect(() => (isOpen ? bodyScroll.block() : bodyScroll.allow()));
</script>

<div>
  <button aria-label="menu" onclick={() => (isOpen = !isOpen)}>
    <div class="wormhole" class:active={isOpen}>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        stroke="var(--accent-pink)"
        stroke-width="2.5"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
        />
      </svg>
      <div class="rings">
        <div class="ring"></div>
        <div class="ring"></div>
        <div class="ring"></div>
      </div>
    </div>
  </button>
  <div class="menu-container" class:open={isOpen}>
    <menu>
      <li>ABOUT ME</li>
      <li>EXPERIENCE</li>
      <li>SERVICES</li>
      <li>CONTACT</li>
    </menu>
  </div>
</div>

<style>
  button {
    cursor: pointer;
    border: none;
    background: none;
    z-index: 99;
  }
  .wormhole {
    width: 60px;
    height: 85px;
    border-radius: 50%;
    background: radial-gradient(
      circle at center,
      var(--bg-gray) 0%,
      var(--bg-primary) 60%,
      transparent 100%
    );
    box-shadow: 0 0 60px 20px #a64dff66;
    transform-style: perspective(3d);
    transform: rotate(0deg);
  }
  .rings {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    transform: translate(-50%, -50%);
  }
  .ring {
    position: absolute;
    width: 100%;
    height: 100%;
    border: 2px solid var(--accent-pink);
    border-radius: 50%;
    animation: pulseRing 5s infinite cubic-bezier(0.075, 0.82, 0.165, 1);
  }
  .ring:nth-child(2) {
    transform: scale(1.2);
    animation-delay: 0.5s;
    border: 4px solid var(--accent-pink);
  }
  .ring:nth-child(3) {
    transform: scale(1.4);
    animation-delay: 1s;
    border: 1px solid var(--accent-pink);
  }
  svg {
    width: 50%;
    height: 100%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  line {
    stroke-width: 5;
    stroke-linecap: round;
    stroke: var(--accent-pink);
    transition: all 0.3s ease;
  }
  .wormhole.active .top {
    transform: rotate(45deg);
    transform-origin: center center;
    width: 50%;
  }
  .wormhole.active .bottom {
    transform: rotate(-45deg);
    transform-origin: center center;
  }
  .wormhole.active .middle {
    opacity: 0;
  }

  @keyframes pulseRing {
    0%,
    100% {
      opacity: 0.2;
      transform: rotate(180deg) translateZ(-150px);
    }
    50% {
      opacity: 1;
      transform: rotate(360deg) translateZ(300px);
    }
  }
  .menu-container {
    position: fixed;
    top: 0;
    right: 0;
    inset: 0;
    width: 100svw;
    height: 100svh;
    overflow: hidden;
    z-index: -1;
    background-color: var(--accent-pink);
    transition: all 500ms ease;
    transform: scaleX(0);
    transform-origin: right top;
    opacity: 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .menu-container.open {
    transform: scaleX(1);
    opacity: 1;
  }
  .menu-container::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: var(--bg-primary);
    transition: all 500ms ease;
    transition-delay: 300ms;
    transform-origin: right top;
    transform: scaleX(0);
    opacity: 0;
    z-index: -1;
  }
  .menu-container.open::before {
    transform: scaleX(1);
    opacity: 1;
  }
  menu {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: var(--text-primary);
    list-style: none;
    font-size: 3.5rem;
    font-family: "Audiowide";
    overflow: hidden;
  }
  .menu-container menu li {
    opacity: 0;
    transform: translateY(20px);
    user-select: none;
    z-index: 3;
    cursor: pointer;
    line-height: 1.5;
    position: relative;
    color: var(--accent-pink);
  }
  .menu-container menu li::before {
    content: "";
    width: 0%;
    height: 5px;
    border-radius: 5px;
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    opacity: 0;
    bottom: 0;
    transition: all 500ms ease;
    transform-origin: center;
  }
  .menu-container menu li:hover {
    color: var(--accent-blue);
  }
  .menu-container menu li:hover::before {
    background-color: var(--accent-blue);
    opacity: 1;
    width: 150%;
  }
  .menu-container.open menu li {
    animation: fadeInUp 1s forwards;
  }

  .menu-container.open menu li:nth-child(1) {
    animation-delay: 0ms;
  }
  .menu-container.open menu li:nth-child(2) {
    animation-delay: 200ms;
  }
  .menu-container.open menu li:nth-child(3) {
    animation-delay: 400ms;
  }
  .menu-container.open menu li:nth-child(4) {
    animation-delay: 600ms;
  }
  .menu-container.open menu li:nth-child(5) {
    animation-delay: 800ms;
  }

  @keyframes fadeInUp {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
</style>
