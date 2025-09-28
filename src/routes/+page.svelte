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
 <section id="proyectos" class="max-w-4xl mx-auto py-12 px-4">
    <h2 class="text-3xl font-bold text-center text-gray-900 mb-8">
      Proyectos Destacados
    </h2>
    
    {#if isLoading}
      <p class="text-center">Cargando proyectos...</p>
    {:else if error}
      <p class="text-center text-red-500">Error: {error}</p>
    {:else}
      <div class="grid gap-8">
        {#each projects as project}
          <ProjectCard {project} />
        {/each}
      </div>
    {/if}
  </section>
</main>