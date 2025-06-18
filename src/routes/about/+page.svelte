<script lang="ts">
  import AOS from 'aos';
  import 'aos/dist/aos.css';
  import { onMount } from 'svelte';

  onMount(() => {
    AOS.init({ duration: 1000, once: true });
  });
</script>

<style>
  .about-container {
    max-width: 1000px;
    margin: auto;
    padding: 4rem 1rem;
    font-family: 'Segoe UI', sans-serif;
    color: #222;
    animation: fadeIn 1.2s ease-in-out;
  }

  .about-title {
    font-size: 2.8rem;
    font-weight: 800;
    text-align: center;
    margin-bottom: 2rem;
    color: #0f2027;
    background: linear-gradient(90deg, #0f2027, #203a43, #2c5364);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .about-section {
    margin-bottom: 3rem;
    display: flex;
    gap: 2rem;
    align-items: center;
    flex-wrap: wrap;
  }

  .about-section.reverse {
    flex-direction: row-reverse;
  }

  .about-text {
    flex: 1;
    font-size: 1.1rem;
    line-height: 1.7;
    color: #444;
  }

  .about-img {
    flex: 1;
    max-width: 400px;
    border-radius: 12px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
    transition: transform 0.4s ease;
  }

  .about-img:hover {
    transform: scale(1.05);
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @media (max-width: 768px) {
    .about-title {
      font-size: 2rem;
    }
    .about-section {
      flex-direction: column;
    }
    .about-section.reverse {
      flex-direction: column;
    }
  }
</style>

<div class="about-container">
  <h1 class="about-title" data-aos="zoom-in">About Me</h1>

  <div class="about-section" data-aos="fade-right">
    <img
      class="about-img"
      src="https://images.pexels.com/photos/1181671/pexels-photo-1181671.jpeg"
      alt="Coding Setup"
    />
    <div class="about-text">
      <p>
        I'm <strong>Developer Prasoon</strong>, a passionate full-stack developer who builds modern web,
        cross-platform, and native applications. I love combining clean code with creative UI/UX to craft
        seamless experiences.
        Also I am in 11th Grade .
      </p>
    </div>
  </div>

  <div class="about-section reverse" data-aos="fade-left">
    <img
      class="about-img"
      src="https://images.pexels.com/photos/3861956/pexels-photo-3861956.jpeg"
      alt="Development Projects"
    />
    <div class="about-text">
      <p>
        With strong skills in AI, ML, Data Science, Blockchain, and DevOps, I can build and deploy fully
        functional applications efficiently. I’m also experienced with a wide variety of frameworks and
        technologies including Svelte, Flutter, React, Node.js, Python, TensorFlow.js, and more.
      </p>
    </div>
  </div>

  <div class="about-section" data-aos="fade-up">
    <img
      class="about-img"
      src="https://images.pexels.com/photos/3747446/pexels-photo-3747446.jpeg"
      alt="Workstation"
    />
    <div class="about-text">
      <p>
        I’m a quick learner and problem solver, continuously exploring new technologies to stay updated.
        I often challenge myself with complex projects and enjoy building things people love to use. Whether it’s
        a single-page app or an enterprise-grade system, I give it my all.
      </p>
    </div>
  </div>
</div>
