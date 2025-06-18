<script lang="ts">
  import { onMount } from 'svelte';
  import { page } from '$app/stores';
  import AOS from 'aos';
  import 'aos/dist/aos.css';
  import gsap from 'gsap';

  let menuOpen = false;
  let darkMode = false;

  onMount(() => {
    AOS.init({ duration: 1000, once: true });
    gsap.from(".navbar", { y: -60, opacity: 0, duration: 1 });
  });

  function toggleMenu() {
    menuOpen = !menuOpen;
  }

  function toggleDarkMode() {
    darkMode = !darkMode;
    document.body.classList.toggle('dark', darkMode);
  }
</script>

<style>
  nav.navbar {
    position: sticky;
    top: 0;
    z-index: 50;
    background: linear-gradient(to right, #203a43, #2c5364);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    color: white;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
  }

  .logo {
    font-size: 1.4rem;
    font-weight: bold;
  }

  .nav-links {
    display: flex;
    gap: 1.5rem;
    align-items: center;
  }

  .nav-links a {
    color: white;
    text-decoration: none;
    font-weight: 600;
    position: relative;
  }

  .nav-links a::after {
    content: "";
    position: absolute;
    height: 2px;
    width: 0%;
    left: 0;
    bottom: -4px;
    background: white;
    transition: width 0.3s ease;
  }

  .nav-links a:hover::after {
    width: 100%;
  }

  .menu-btn {
    display: none;
    font-size: 1.5rem;
    cursor: pointer;
  }

  .nav-links button {
    background: #fff;
    color: #111;
    padding: 0.3rem 1rem;
    border-radius: 9999px;
    font-weight: bold;
    cursor: pointer;
  }

  @media (max-width: 768px) {
    .menu-btn {
      display: block;
    }

    .nav-links {
      position: absolute;
      top: 64px;
      left: 0;
      right: 0;
      background: #2c5364;
      flex-direction: column;
      align-items: center;
      padding: 1rem;
      gap: 1rem;
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.3s ease-in-out;
    }

    .nav-links.open {
      max-height: 300px;
    }
  }

  body.dark {
    background-color: #121212;
    color: white;
  }

  body.dark nav.navbar {
    background: #1e1e1e;
  }

  body.dark .nav-links a {
    color: #ccc;
  }
</style>

<nav class="navbar" data-aos="fade-down">
  <div class="logo">⚡ Prasoon Dev</div>

  <div class="menu-btn" on:click={toggleMenu}>
    {#if menuOpen}
      ✖
    {:else}
      ☰
    {/if}
  </div>

  <div class="nav-links {menuOpen ? 'open' : ''}">
    <a href="/">Home</a>
    <a href="/about">About</a>
    <a href="/projects">Projects</a>
    <a href="/contact">Contact</a>
    <button on:click={toggleDarkMode}>
      {darkMode ? '🌞 Light' : '🌙 Dark'}
    </button>
  </div>
</nav>

<slot />
