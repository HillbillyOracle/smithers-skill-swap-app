<script>
  import '../app.css';
  export let data;
</script>

<div class="min-h-screen font-body bg-gray-50 text-gray-800">
  <slot />
</div>
=======
=======
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

<nav class="bg-purple-600 text-white p-4 flex gap-4">
  <a href="/" class="font-bold">Home</a>
  <a href="/profile" class="bg-white text-purple-600 px-3 py-1 rounded font-bold">Profile</a>
  <a href="/instructors" class="bg-white text-purple-600 px-3 py-1 rounded font-bold">Browse Instructors</a>
</nav>
<main class="p-4">
  <slot />
</main>