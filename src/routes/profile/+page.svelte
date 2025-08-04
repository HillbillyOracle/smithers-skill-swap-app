<script>
  import { supabase } from '$lib/supabase';
  let email = '';
  let name = '';
  let bio = '';
  let isPublic = false;

  async function loadProfile() {
    if (!email) return;
    const { data } = await supabase
      .from('profiles')
      .select('*')
      .eq('email', email)
      .single();
    if (data) {
      name = data.name || '';
      bio = data.bio || '';
      isPublic = data.is_public || false;
    }
  }

  async function saveProfile() {
    const { error } = await supabase.from('profiles').upsert({
      email,
      name,
      bio,
      is_public: isPublic
    });
    if (!error) {
      alert('Profile saved');
    }
  }
</script>

<h2 class="text-2xl font-bold text-purple-700">Your Profile</h2>
<form on:submit|preventDefault={saveProfile} class="space-y-4 mt-4 max-w-md">
  <input
    type="email"
    placeholder="Email"
    bind:value={email}
    class="border p-2 w-full"
    required
    on:blur={loadProfile}
  />
  <input
    type="text"
    placeholder="Name"
    bind:value={name}
    class="border p-2 w-full"
  />
  <textarea
    placeholder="Bio"
    bind:value={bio}
    class="border p-2 w-full"
  ></textarea>
  <label class="flex items-center">
    <input type="checkbox" bind:checked={isPublic} class="mr-2" />
    Make profile public
  </label>
  <button
    type="submit"
    class="bg-green-600 hover:bg-green-700 text-white font-bold py-2 px-4 rounded"
  >
    Save
  </button>
</form>
