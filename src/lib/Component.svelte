<script lang="ts">
  import type { NumArr } from "$lib";

  let { ids }: { ids: NumArr } = $props();

  // BUG: this line throws during navigation (due to $inspect())
  const getFirstId = (arr: NumArr) => arr[0];

  // this line is ok
  const firstId = $derived(getFirstId(ids));
  // but this line triggers the above after `ids` is undefined (somehow)
  // Remove it, to get rid of the bug
  $inspect(firstId);
</script>
