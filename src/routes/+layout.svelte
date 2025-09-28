<script>
  import '../app.css';
  import Header from '$lib/components/Header.svelte'; // 1. Importar Header
  import Footer from '$lib/components/Footer.svelte'; // 2. Importar Footer
</script>

<Header /> <slot />

<Footer /> 
