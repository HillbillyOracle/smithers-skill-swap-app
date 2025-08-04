<script>
  import '../app.css';
  export let data;
</script>

<div class="min-h-screen font-body bg-gray-50 text-gray-800">
  <slot />
</div>
=======
<nav class="bg-purple-600 text-white p-4 flex gap-4">
  <a href="/" class="font-bold">Home</a>
  <a href="/profile" class="bg-white text-purple-600 px-3 py-1 rounded font-bold">Profile</a>
  <a href="/instructors" class="bg-white text-purple-600 px-3 py-1 rounded font-bold">Browse Instructors</a>
</nav>
<main class="p-4">
  <slot />
</main>
