<header>
  <nav>
    <a href="/" class="logo">Rodrigo Armoa</a>
    <div class="links">
      <a href="#proyectos">Proyectos</a>
      <a href="#contacto">Contacto</a>
    </div>
  </nav>
</header>

<style>
  header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: rgba(17, 24, 39, 0.8);
    backdrop-filter: blur(10px);
    z-index: 50;
    border-bottom: 1px solid var(--border-color);
  }
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 900px;
    margin: 0 auto;
    padding: 1rem;
  }
  .logo {
    font-weight: 700;
    font-size: 1.25rem;
  }
  .links {
    display: flex;
    gap: 1.5rem;
  }
</style>