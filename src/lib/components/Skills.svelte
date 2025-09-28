<script>
  // Importamos los logos directamente. SvelteKit se encarga de optimizarlos.
  import java_logo from '$lib/assets/logos/java.svg';
  import spring_logo from '$lib/assets/logos/spring.svg';
  import svelte_logo from '$lib/assets/logos/svelte.svg';
  import mysql_logo from '$lib/assets/logos/mysql.svg';
  import github_logo from '$lib/assets/logos/github.svg';
  import docker_logo from '$lib/assets/logos/docker.svg';
  import jira_logo from '$lib/assets/logos/jira.svg';
  import androidstudio_logo from '$lib/assets/logos/androidstudio.svg';
  import postman_logo from '$lib/assets/logos/postman.svg';
  import html_logo from '$lib/assets/logos/html.svg';
  import css_logo from '$lib/assets/logos/css3.svg';
  import oracle_logo from '$lib/assets/logos/oracle.svg';
  import sonarqube_logo from '$lib/assets/logos/sonarqube.svg';
  

  // Creamos una lista de objetos, donde cada objeto tiene el nombre y el logo.
  const skills = [
    { name: 'Java', logo: java_logo },
    { name: 'Spring Boot', logo: spring_logo },
    { name: 'SvelteKit', logo: svelte_logo },
    { name: 'MySQL', logo: mysql_logo },
    { name: 'Git', logo: github_logo },
    { name: 'Docker', logo: docker_logo },
    { name: 'Jira', logo: jira_logo },
    { name: 'Android Studio', logo: androidstudio_logo },
    { name: 'Postman', logo: postman_logo },  
    { name: 'HTML5', logo: html_logo },
    { name: 'CSS3', logo: css_logo },
    { name: 'Oracle DB', logo: oracle_logo },
    { name: 'SonarQube', logo: sonarqube_logo }
    
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
    color: #f0f0f0; /* Un color claro para el título */
  }

  .skills-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem; /* Espacio entre los logos */
  }

  .skill-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.75rem; /* Espacio entre el logo y el texto */
    padding: 1rem;
    background-color: #2d3748; /* Un fondo ligeramente más claro */
    border-radius: 8px;
    width: 120px; /* Ancho fijo para cada tarjeta */
    transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
  }
  
  .skill-card:hover {
    transform: translateY(-5px); /* Efecto de "levantar" al pasar el ratón */
    box-shadow: 0 10px 15px rgba(0,0,0,0.2);
  }

  .skill-logo {
    width: 60px;  /* Tamaño del logo */
    height: 60px; /* Tamaño del logo */
  }
  
  .skill-card span {
    color: #e2e8f0;
    font-weight: 500;
  }
</style>