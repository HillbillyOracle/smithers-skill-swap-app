<script>
  import { page } from '$app/stores';
  import { supabase } from '$lib/supabase';
  let event;
  $: id = $page.params.id;
  supabase.from('events').select('*').eq('id', id).single().then(({ data }) => event = data);
</script>

{#if event}
  <h2>{event.title}</h2>
  <p>{event.description}</p>
  <!-- RSVP form stub -->
{/if}
