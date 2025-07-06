<script>
  export let data;
</script>

<div class="app-container">
  <slot />
</div>

<style>
  .app-container {
    min-height: 100vh;
    background-color: #002855;
    color: white;
    font-weight: bold;
    font-family: sans-serif;
    padding: 1rem;
  }

  a {
    color: #38bdf8;
  }

  ul {
    list-style-type: disc;
    margin-left: 1.5rem;
  }

  .btn-lime {
    background-color: #84cc16;
    color: #002855;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
  }

  .btn-yellow {
    background-color: #facc15;
    color: #002855;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
  }

  .btn-bright-blue {
    background-color: #0ea5e9;
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
  }
</style>
