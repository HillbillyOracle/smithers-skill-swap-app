<script>
  import { page } from '$app/stores';
  import { supabase } from '$lib/supabase';
  let event;
  $: id = $page.params.id;
  supabase.from('events').select('*').eq('id', id).single().then(({ data }) => event = data);
</script>

{#if event}
  <h2 class="text-2xl mb-4">{event.title}</h2>
  <p class="mb-4">{event.description}</p>
  <button class="btn-yellow">RSVP</button>
{/if}
