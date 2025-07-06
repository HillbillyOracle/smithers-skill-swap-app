<script>
  import { supabase } from '$lib/supabase';
  let events = [];
  supabase.from('events').select('*').then(({ data }) => events = data);
</script>

<h2>Upcoming Events</h2>
<ul>
  {#each events as event}
    <li><a href="/events/{event.id}">{event.title}</a></li>
  {/each}
</ul>
