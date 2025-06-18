<script lang="ts">
  import { onMount } from 'svelte';
  import AOS from 'aos';
  import 'aos/dist/aos.css';
  import gsap from 'gsap';

  onMount(() => {
    AOS.init({ duration: 1000 });
    gsap.from(".projects-heading", { y: -30, opacity: 0, duration: 1 });
    gsap.from(".project-card", {
      y: 40,
      opacity: 0,
      duration: 1,
      stagger: 0.2,
      delay: 0.5
    });
  });

  const projects = [
    {
      title: "Travel journal ",
      description: "A Traveel journal with React , leaflet and bulma css .",
      image: "https://via.placeholder.com/300x200",
      link: "https://travel-journal-ruddy-seven.vercel.app/"
    },
    {
      title: "Bloggers",
      description: "An Blogging app by sveltekit , typescript and materialize css",
      image: "https://via.placeholder.com/300x200",
      link: "https://blogers-npsj.vercel.app/"
    },
    {
      title: "markup",
      description: "A markdown preview app using svelte kit , typescript and materialize.css",
      image: "https://via.placeholder.com/300x200",
      link: "https://biz-tracker-vert.vercel.app/"
    },
    // Add more project objects here
  ];
</script>

<style>
  .projects {
    padding: 4rem 1.5rem;
    background: #f4f4f4;
    text-align: center;
  }

  .projects-heading {
    font-size: 2.5rem;
    margin-bottom: 3rem;
    color: #2c5364;
  }

  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 2rem;
    max-width: 1200px;
    margin: 0 auto;
  }

  .project-card {
    background: white;
    border-radius: 1rem;
    box-shadow: 0 6px 16px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    transition: transform 0.3s ease;
  }

  .project-card:hover {
    transform: translateY(-10px);
  }

  .project-card img {
    width: 100%;
    height: 180px;
    object-fit: cover;
  }

  .project-content {
    padding: 1.2rem;
  }

  .project-title {
    font-size: 1.3rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
    color: #203a43;
  }

  .project-desc {
    font-size: 0.95rem;
    margin-bottom: 1rem;
    color: #555;
  }

  .project-link {
    display: inline-block;
    padding: 0.6rem 1.2rem;
    background-color: #2c5364;
    color: white;
    text-decoration: none;
    border-radius: 9999px;
    font-weight: bold;
    transition: background 0.3s ease;
  }

  .project-link:hover {
    background-color: #1e3c4c;
  }
</style>

<section class="projects" data-aos="fade-up">
  <h1 class="projects-heading">🚀 My Projects</h1>
  <div class="projects-grid">
    {#each projects as project}
      <div class="project-card" data-aos="zoom-in">
        <img src={project.image} alt={project.title} />
        <div class="project-content">
          <h3 class="project-title">{project.title}</h3>
          <p class="project-desc">{project.description}</p>
          <a class="project-link" href={project.link} target="_blank">View Project</a>
        </div>
      </div>
    {/each}
  </div>
</section>
