<script>


  // Creamos la lista de objetos, pero ahora el 'logo' es una simple URL de texto.
  const skills = [
    { name: 'Java', logo: '/logos/java.svg' },
    { name: 'Spring Boot', logo: '/logos/spring.svg' },
    { name: 'SvelteKit', logo: '/logos/svelte.svg' },
    { name: 'MySQL', logo: '/logos/mysql.svg' },
    { name: 'Git', logo: '/logos/github.svg' },
    { name: 'Docker', logo: '/logos/docker.svg' },
    { name: 'Jira', logo: '/logos/jira.svg' },
    { name: 'Android Studio', logo: '/logos/androidstudio.svg' },
    { name: 'Postman', logo: '/logos/postman.svg' },
    { name: 'HTML5', logo: '/logos/html.svg' },
    { name: 'CSS3', logo: '/logos/css3.svg' },
    { name: 'Oracle DB', logo: '/logos/oracle.svg' },
    { name: 'SonarQube', logo: '/logos/sonarqube.svg' }
  ];
</script>

<section id="habilidades" class="skills-container">
  <h2 class="section-title">Habilidades Técnicas</h2>
  
  <div class="skills-grid">
    {#each skills as skill}
      <div class="skill-card">
        <img src={skill.logo} alt="{skill.name} logo" class="skill-logo" />
        <span>{skill.name}</span>
      </div>
    {/each}
  </div>
</section>

<style>
  .skills-container {
    max-width: 900px;
    margin: 4rem auto;
    padding: 2rem;
    text-align: center;
  }
  .section-title {
    font-size: 2.5rem;
    font-weight: bold;
    margin-bottom: 3rem;
    color: #f0f0f0;
  }
  .skills-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem;
  }
  .skill-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.75rem;
    padding: 1rem;
    background-color: #2d3748;
    border-radius: 8px;
    width: 120px;
    transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
  }
  .skill-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 15px rgba(0,0,0,0.2);
  }
  .skill-logo {
    width: 60px;
    height: 60px;
  }
  .skill-card span {
    color: #e2e8f0;
    font-weight: 500;
  }
</style>