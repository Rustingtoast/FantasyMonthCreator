<script lang="ts">
  let { year = $bindable(0) } = $props<{ year?: number }>();
</script>

<div class="space-y-3">
  <label class="label p-0" for="year-value">
    <span class="label-text font-medium">Year</span>
  </label>

  <input id="year-value" class="input input-bordered w-full" type="number" bind:value={year} />

  <input
    class="range range-primary"
    type="range"
    min="-100000"
    max="100000"
    step="1"
    bind:value={year}
  />
</div>
