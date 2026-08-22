<script lang="ts">
  import type { Month } from "$lib/types/month";

  let { months, onRemove } = $props<{ months: Month[]; onRemove: (index: number) => void }>();
</script>

<div class="overflow-auto max-h-80">
  <table class="table table-zebra table-pin-rows table-sm">
    <thead>
      <tr>
        <th>Nr</th>
        <th>Name</th>
        <th>Days</th>
        <th class="w-1">Actions</th>
      </tr>
    </thead>
    <tbody>
      {#if months.length === 0}
        <tr>
          <td colspan="4" class="text-center opacity-70">No months saved yet.</td>
        </tr>
      {:else}
        {#each months as month, index (index)}
          <tr>
            <th>{index + 1}</th>
            <td>{month.month}</td>
            <td>{month.days}</td>
            <td>
              <button class="btn btn-ghost btn-xs text-error" onclick={() => onRemove(index)}>Remove</button>
            </td>
          </tr>
        {/each}
      {/if}
    </tbody>
  </table>
</div>
