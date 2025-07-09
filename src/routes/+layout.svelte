<script>
    import 'bootstrap/dist/css/bootstrap.min.css'
    import 'bootstrap-icons/font/bootstrap-icons.css'
    import {onMount} from 'svelte'

    onMount(async()=>{
        await import('bootstrap/dist/js/bootstrap.bundle.min.js')
    })
</script>

<!--Navbar-->
<nav class="navbar navbar-expand-lg bg-body-tertiary">
  <div class="container-fluid">
    <!-- <img src="favicon.svg" class="mw-1" alt=""> -->
    <a class="navbar-brand" href="/">Denny Mario
    </a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link" aria-current="page" href="/">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/">Projects</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/">About</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/">Contacts</a>
        </li>
      </ul>
    </div>
  </div>
</nav>

<main class="container mt-4 py-2 px-2">
    <slot/>
</main>

<!--Footer-->
<footer>

</footer>