<script>
  import "prism-themes/themes/prism-one-dark.css";
</script>

<svelte:head>
  <link rel="stylesheet" href="/pico.min.css" />

  <style>
    nav {
      margin-left: 42%;
      margin-right: 15%;
    }
  </style>
</svelte:head>

<nav>
  <ul>
    <li><a href="/">Hem</a></li>
    <li><a href="/devblog">Min blog</a></li>
  </ul>
</nav>

<main class="container-fluid">
  <hr />

  <main class="container">
    <slot />
  </main>
</main>
