<script>
  import 'bootstrap/dist/css/bootstrap.min.css'
  import 'bootstrap-icons/font/bootstrap-icons.css'
  import { onMount } from 'svelte'

  onMount(async () => {
    await import('bootstrap/dist/js/bootstrap.bundle.min.js')
  })

  let year = new Date().getFullYear()
</script>

<!--Navbar-->
<nav class="navbar navbar-expand-lg bg-body-tertiary">
  <div class="container-fluid">
    <a class="navbar-brand" href="/">Denny Mario</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link" aria-current="page" href="/">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/projects">Projects</a>
        </li>
      </ul>
    </div>
  </div>
</nav>

<main class="container mt-4 py-4 px-3 bg-light rounded shadow-sm flex-fill">
  <slot/>
</main>

<footer class="text-center py-3 mt-auto border-top bg-light">
  <small>© {year} Denny Mario</small>
</footer>

<style>
  :global(body) {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  main {
    flex: 1;
  }
</style>
