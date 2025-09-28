<script>
  import { onMount } from 'svelte';
  import ProjectCard from '$lib/components/ProjectCard.svelte';
  import Hero from '$lib/components/Hero.svelte';
  import Skills from '$lib/components/Skills.svelte';

  /** @type {any[]} */
  let projects = [];
  let isLoading = true;
  
  /** @type {string | null} */
  let error = null;

  onMount(async () => {
    try {
      const response = await fetch('http://localhost:8082/api/projects');
      if (!response.ok) throw new Error('No se pudo conectar con la API');
      projects = await response.json();
    } catch (e) {
      if (e instanceof Error) {
        error = e.message;
      }
    } finally {
      isLoading = false;
    }
  });
</script>

<main>
  <Hero />
  <Skills />
  <section>
    <h2>Proyectos Destacados</h2>
    {#if isLoading}
      <p>Cargando proyectos...</p>
    {:else if error}
      <p style="color: red;">Error: {error}</p>
    {:else}
      <div style="display: grid; gap: 1.5rem;">
        {#each projects as project}
          <ProjectCard {project} />
        {/each}
      </div>
    {/if}
  </section>
</main>