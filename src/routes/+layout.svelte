<script>
  import "prism-themes/themes/prism-one-dark.css";
</script>

<svelte:head>
  <link rel="stylesheet" href="/pico.min.css" />


</svelte:head>
  <style>
    nav {
      margin-left: 40%;
      margin-right: 15%;
      
      
    }
    a{
      color: black;
    }

    
  </style>
<nav>
  <ul>
    <li><a href="/hemsida">Hem</a></li>
    <li><a href="/Info">Floorball and more</li>
  </ul>
</nav>

<main class="container-fluid">
  <hr />

  <main class="container">
    <slot />
  </main>
</main>
