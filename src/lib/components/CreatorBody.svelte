<script lang="ts">
  import type { Month } from "$lib/types/month";

  const firstParts = ["j", "nov", "dec", "febr", "m", "sept"];
  const secondParts = ["octo", "em", "uly", "a", "une", "an"];
  const thirdParts = ["ber", "y", "unary", "rch", "pril", "ugust"];

  let { onSave } = $props<{ onSave: (month: Month) => void }>();

  let monthNamePartOne = $state(firstParts[0]);
  let monthNamePartTwo = $state(secondParts[0]);
  let monthNamePartThree = $state(thirdParts[0]);
  let selectedDays = $state(30);

  const fullMonthName = $derived(`${monthNamePartOne}${monthNamePartTwo}${monthNamePartThree}`.trim());
  const canSave = $derived(fullMonthName.length > 0 && selectedDays > 0);

  function saveAndUpload() {
    if (!canSave) return;

    onSave({
      month: fullMonthName,
      days: selectedDays,
    });
  }
</script>

<div class="space-y-4">
  <div>
    <label class="label p-0 pb-2" for="month-name-part-one">
      <span class="label-text font-medium">Month</span>
    </label>

    <div class="grid grid-cols-3 gap-2">
      <select id="month-name-part-one" class="select select-bordered h-36" size="6" bind:value={monthNamePartOne}>
        {#each firstParts as monthPart}
          <option>{monthPart}</option>
        {/each}
      </select>
      <select class="select select-bordered h-36" size="6" bind:value={monthNamePartTwo}>
        {#each secondParts as monthPart}
          <option>{monthPart}</option>
        {/each}
      </select>
      <select class="select select-bordered h-36" size="6" bind:value={monthNamePartThree}>
        {#each thirdParts as monthPart}
          <option>{monthPart}</option>
        {/each}
      </select>
    </div>
  </div>

  <div>
    <label class="label p-0 pb-2" for="days-in-month">
      <span class="label-text font-medium">Days</span>
    </label>
    <input id="days-in-month" class="input input-bordered w-full max-w-24" type="number" min="1" bind:value={selectedDays} />
  </div>

  <div class="card-actions justify-end">
    <button class="btn btn-primary" onclick={saveAndUpload} disabled={!canSave}>Save</button>
  </div>
</div>
