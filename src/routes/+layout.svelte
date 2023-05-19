<script>
	import Footer from '$lib/Footer.svelte';
  import Nav from '$lib/Nav.svelte';
  import '../app.css';
</script>

<div class="overflow-hidden relative w-full h-screen font-spacemono flex flex-col">
  <div>
    <Nav />
  </div>
  <div class="scrollbar overflow-y-scroll">
    <slot />
  </div>
  <div>
    <Footer />
  </div>
</div>
