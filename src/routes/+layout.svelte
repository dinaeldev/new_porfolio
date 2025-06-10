<script lang="ts">
    import Header from '$lib/layout/Header.svelte';

  let { children } = $props();
</script>

<Header />
<main>
  {@render children()}
</main>