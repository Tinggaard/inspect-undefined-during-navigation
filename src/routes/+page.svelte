<script lang="ts">
  import { resolve } from "$app/paths";
  import Component from "$lib/Component.svelte";

  let { data } = $props();
  let { ids } = $derived(data);
</script>

<Component {ids} />

<a href={resolve("/[id]", { id: `foobar` })} class="underline"> Navigate! </a>
