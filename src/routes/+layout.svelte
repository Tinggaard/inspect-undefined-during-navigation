<script lang="ts">
  import "./layout.css";
  import favicon from "$lib/assets/favicon.svg";

  let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<svelte:boundary onerror={(e) => console.error(e)}>
  {#snippet failed(err)}
    <pre>{err}</pre>

    {#if err instanceof Error}
      <p>Stack:</p>
      <pre>{err.stack}</pre>
    {/if}
  {/snippet}

  <main class="m-4">
    {@render children()}
  </main>
</svelte:boundary>
