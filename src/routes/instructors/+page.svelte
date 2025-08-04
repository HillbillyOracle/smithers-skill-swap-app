<script>
  import { supabase } from '$lib/supabase';
  let profiles = [];
  supabase
    .from('profiles')
    .select('email, name, bio')
    .eq('is_public', true)
    .then(({ data }) => (profiles = data || []));
</script>

<h2 class="text-2xl font-bold text-purple-700">Browse Instructors</h2>
<div class="grid gap-4 mt-4 md:grid-cols-2">
  {#each profiles as profile}
    <div class="border p-4 rounded shadow bg-blue-50">
      <h3 class="text-xl font-bold">{profile.name}</h3>
      <p class="mb-2">{profile.bio}</p>
      <a
        href="mailto:{profile.email}"
        class="inline-block bg-blue-600 hover:bg-blue-700 text-white font-bold py-1 px-3 rounded"
        >Contact</a
      >
    </div>
  {/each}
</div>
