<script>
    import { Link } from "svelte-routing";
  </script>
  <nav class="navbar shadow navbar-expand-lg navbar-light bg-light">
	<div class="container">
	  <Link class="navbar-brand" to="/"><img class="img-fluid" src="https://getbootstrap.com/docs/5.1/assets/img/favicons/favicon.ico" alt="bootstrap svelte"/> ootstrap Svelte</Link>
	  <button class="navbar-toggler btn rounded-circle" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <svg xmlns="http://www.w3.org/2000/svg" width="26" height="26" fill="currentColor" class="bi bi-filter-right" viewBox="0 0 16 16">
            <path d="M14 10.5a.5.5 0 0 0-.5-.5h-3a.5.5 0 0 0 0 1h3a.5.5 0 0 0 .5-.5zm0-3a.5.5 0 0 0-.5-.5h-7a.5.5 0 0 0 0 1h7a.5.5 0 0 0 .5-.5zm0-3a.5.5 0 0 0-.5-.5h-11a.5.5 0 0 0 0 1h11a.5.5 0 0 0 .5-.5z"/>
          </svg>
	  </button>
	  <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
		<ul class="navbar-nav p-3">
		  <li class="nav-item">
			<Link class="nav-link active" to="/">Home</Link>
		  </li>
		  <li class="nav-item">
			<Link class="nav-link active" to="/start">About</Link>
		  </li>
		  <li class="nav-item">
			<Link class="nav-link active" to="/freedom">Freedom</Link>
		  </li>
		  <li class="nav-item">
			<a class="nav-link active" href="https://github.com/mesinkasir/bootstrapsvelte">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-github" viewBox="0 0 16 16">
                    <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
                  </svg> Github
            </a>
		  </li>
		  <li class="nav-item">
			<a class="nav-link active" href="https://www.hockeycomputindo.com/2021/10/svelte-bootstrap-free-download-source.html">
             Documentation  →
            </a>
		  </li>
	</ul>
	  </div>
	</div>
  </nav>