<script>
  export let project;
</script>
<article class="project-card">
  <h2>{project.name}</h2>
  <p>{project.description}</p>
  <div class="tech-tags">
    <strong>Tecnologías:</strong>
    {#each project.technologies as tech}
      <span class="tech-tag">{tech}</span>
    {/each}
  </div>
  <a href={project.githubUrl} target="_blank" rel="noopener noreferrer">Ver código en GitHub &rarr;</a>
</article>