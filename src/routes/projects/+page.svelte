<script>
  import { onMount } from 'svelte';

  let projects = [];

  onMount(async () => {
    const res = await fetch('json/projects.json');
    const data = await res.json();
    projects = data.myProjects;
  });

  function getBadgeClass(progress) {
    switch (progress) {
      case 'done':
        return 'bg-success';
      case 'ongoing':
        return 'bg-warning text-dark';
      default:
        return 'bg-secondary';
    }
  }
</script>

<div class="container my-4">
  <div class="row gy-4">
    {#each projects as project}
      <div class="col-md-6">
        <div class="card shadow-sm h-100">
          <div class="card-body">
            <h5 class="card-title d-flex justify-content-between align-items-center">
              {project.name}
              <span class="badge rounded-pill {getBadgeClass(project.progress)}">
                {project.progress}
              </span>
            </h5>
            <p class="card-text">{project.desc}</p>

            <p>
              <strong>Tools:</strong>
              {#each project.tools as tool}
                <span class="badge bg-light text-dark me-1">{tool}</span>
              {/each}
            </p>

            {#if project.github}
              <a href={project.github} target="_blank" class="btn btn-sm btn-outline-primary me-2">
                GitHub
              </a>
            {/if}

            {#if project.videoUrl}
              <a href={project.videoUrl} target="_blank" class="btn btn-sm btn-outline-secondary">
                Video
              </a>
            {/if}
          </div>
        </div>
      </div>
    {/each}
  </div>
</div>
