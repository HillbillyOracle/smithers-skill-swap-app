<script>
  import { supabase } from '$lib/supabase';
  let events = [];
  supabase.from('events').select('*').then(({ data }) => events = data);
</script>

  <h2 class="text-2xl font-heading text-primary mb-2">Upcoming Events</h2>
  <ul class="space-y-2">
    {#each events as event}
      <li class="p-2 bg-white rounded shadow">
        <a class="text-accent hover:underline" href="/events/{event.id}">{event.title}</a>
      </li>
    {/each}
  </ul>
