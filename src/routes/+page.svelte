<script lang="ts">
  import AOS from 'aos';
  import 'aos/dist/aos.css';

  import gsap from 'gsap';
  import { onMount } from 'svelte';

  onMount(() => {
    AOS.init({
      duration: 1000,
      once: true
    });

    gsap.from(".hero h1", { y: -50, opacity: 0, duration: 1 });
    gsap.from(".hero img", { scale: 0.8, opacity: 0, duration: 1, delay: 0.5 });
    gsap.from(".cta-button", { y: 20, opacity: 0, duration: 1, delay: 0.7 });
  });
</script>

<style>
  .hero {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 4rem 1rem;
    background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
    color: white;
    text-align: center;
  }

  .hero h1 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    font-weight: 700;
  }

  .hero section {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }

  .hero img {
    width: 240px;
    height: 240px;
    object-fit: cover;
    border-radius: 50%;
    box-shadow: 0 0 20px rgba(255, 255, 255, 0.3);
  }

  .cta-button {
    background-color: #ff6347;
    padding: 0.75rem 1.5rem;
    border-radius: 9999px;
    color: white;
    font-weight: bold;
    text-decoration: none;
    transition: background-color 0.3s ease, transform 0.3s ease;
  }

  .cta-button:hover {
    background-color: #ff4500;
    transform: scale(1.05);
  }

  .tech-grid {
    padding: 3rem 1rem;
    display: flex;
    justify-content: center;
    background-color: #f9f9f9;
  }

  .technologies img {
    max-width: 100%;
    height: auto;
  }

  .info-section {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    padding: 3rem 1rem;
    gap: 2rem;
    flex-wrap: wrap;
    background-color: #fff;
  }

  .info-section.reverse {
    flex-direction: row-reverse;
    background-color: #f0f0f0;
  }

  .info-section img {
    width: 300px;
    height: auto;
    border-radius: 1rem;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
  }

  .info-section p {
    max-width: 500px;
    font-size: 1.1rem;
    color: #333;
  }

  footer {
    background-color: #0f2027;
    color: #fff;
    text-align: center;
    padding: 2rem 1rem;
    font-size: 1rem;
    margin-top: 2rem;
  }
  footer {
  background-color: #0f2027;
  color: #fff;
  text-align: center;
  padding: 2rem 1rem;
  font-size: 1rem;
}

.social-links {
  margin-top: 1rem;
  display: flex;
  justify-content: center;
  gap: 1.2rem;
  flex-wrap: wrap;
}

.social-links a img {
  width: 28px;
  height: 28px;
  filter: invert(100%);
  transition: transform 0.3s ease, filter 0.3s ease;
}

.social-links a:hover img {
  transform: scale(1.2);
  filter: invert(60%) sepia(100%) saturate(500%) hue-rotate(350deg);
}
/* global.css or App.svelte <style> */
body.dark {
  background: #121212;
  color: white;
}

</style>

<!-- Hero Section -->
<div class="hero">
  <h1>Hi, I am Developer Prasoon</h1>
  <section>
    <img src="https://images.pexels.com/photos/577585/pexels-photo-577585.jpeg" alt="Profile Image" />
    <a class="cta-button" href="https://prasoonjadonpis6.wordpress.com/" target="_blank">
      Get Started
    </a>
  </section>
</div>

<!-- Tech Grid -->
<div class="tech-grid">
  <div class="technologies" data-aos="fade-up">
    <img
      src="https://skillicons.dev/icons?i=html,css,js,svelte,nodejs,flutter,go,cs,python,java,r,react,nextjs,deno,express,flask,d3,matplotlib,scikitlearn,kotlin,reactnative,tensorflow,ai,githubactions,docker"
      alt="Technologies"
    />
  </div>
</div>

<!-- Info Sections -->
<div class="info-section" data-aos="fade-right">
  <img src="https://images.pexels.com/photos/1181671/pexels-photo-1181671.jpeg" alt="Developer Tools" />
  <p>
    I am a Fullstack developer that can create web, cross-platform and native apps using AI & ML models, with data visualisation and analysis. I'm also skilled in blockchain, Web3, and DevOps.
  </p>
</div>

<div class="info-section reverse" data-aos="fade-left">
  <img src="https://images.pexels.com/photos/3861956/pexels-photo-3861956.jpeg" alt="Project Work" />
  <p>
    I work on various projects across multiple frameworks. With my experience, I can build and deploy fully functional websites in just one day, with excellent performance and design.
  </p>
</div>

<footer>
  <p>© 2025 Developer Prasoon.</p>
  <div class="social-links">
    <a href="https://github.com/Pjdeveloper896" target="_blank" aria-label="GitHub">
      <img src="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/github.svg" alt="GitHub" />
    </a>
    <a href="https://dev.to/Pjdeveloper896" target="_blank" aria-label="Dev.to">
      <img src="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/devdotto.svg" alt="Dev.to" />
    </a>
    <a href="https://www.instagram.com/developer_prasoon/profilecard/?igsh=MThoeXh6YjNqN2M1bw%3D%3D" target="_blank" aria-label="Instagram">
      <img src="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/instagram.svg" alt="Instagram" />
    </a>
    <a href="https://youtube.com/@pjdeveloper896?feature=shared" target="_blank" aria-label="YouTube">
      <img src="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/youtube.svg" alt="YouTube" />
    </a>
  </div>
</footer>

