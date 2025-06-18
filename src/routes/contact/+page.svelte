<script lang="ts">
  import AOS from 'aos';
  import 'aos/dist/aos.css';
  import { onMount } from 'svelte';

  onMount(() => {
    AOS.init({ duration: 1000, once: true });
  });

  function copyEmail() {
    navigator.clipboard.writeText('prasoonjadonpis6@gmail.com');
    alert('📧 Email address copied to clipboard!');
  }
</script>

<style>
  .contact-container {
    max-width: 900px;
    margin: auto;
    padding: 4rem 1rem;
    font-family: 'Segoe UI', sans-serif;
    color: #333;
    text-align: center;
  }

  .contact-title {
    font-size: 2.5rem;
    font-weight: bold;
    margin-bottom: 2rem;
    background: linear-gradient(90deg, #0f2027, #203a43, #2c5364);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .email-box {
    font-size: 1.2rem;
    background-color: #f4f4f4;
    padding: 1rem 2rem;
    border-radius: 10px;
    display: inline-flex;
    align-items: center;
    gap: 1rem;
    margin-top: 1rem;
    cursor: pointer;
    box-shadow: 0 4px 20px rgba(0,0,0,0.05);
    transition: transform 0.2s ease;
  }

  .email-box:hover {
    transform: scale(1.05);
    background: #eaeaea;
  }

  .icon {
    font-size: 1.5rem;
    color: #203a43;
  }

  .email-text {
    font-weight: 600;
    user-select: all;
  }

  .note {
    margin-top: 1rem;
    font-size: 0.95rem;
    color: #555;
  }
</style>

<div class="contact-container">
  <h1 class="contact-title" data-aos="fade-down">📬 Contact Me</h1>

  <div class="email-box" on:click={copyEmail} data-aos="fade-up">
    <span class="icon">📧</span>
    <span class="email-text">Prasoonjadon.pis6@gmail.com</span>
  </div>

  <p class="note" data-aos="fade-up" data-aos-delay="300">
    Click to copy email address to clipboard. And send me What You Want To create.
  </p>
</div>
