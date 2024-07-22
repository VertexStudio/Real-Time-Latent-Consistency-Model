<script lang="ts">
  import type { FieldProps } from '$lib/types';
  import { onMount } from 'svelte';
  export let value: string;
  export let params: FieldProps;
  onMount(() => {
    value = String(params?.default ?? '');
  });
</script>

<div class="">
  <label class="text-base font-medium" for={params?.title}>
    {params?.title}
  </label>
  <div class="text-base flex items-center rounded-md border-2 border-fuchsia-600">
    <textarea
      class="mx-1 w-full px-3 py-2 font-medium outline-none dark:text-white bg-black shadow-md"
      title={params?.title}
      placeholder="Craft your prompt here..."
      bind:value
    ></textarea>
  </div>
</div>