<script>
  import '../app.css';
  import Navigation from '$lib/components/Navigation.svelte';
  import { initDarkMode } from '$lib/utils';
  import { onMount } from 'svelte';

  onMount(() => {
    initDarkMode();
  });
</script>

<Navigation />
<main class="min-h-screen bg-white dark:bg-gray-900">
  <slot />
</main>