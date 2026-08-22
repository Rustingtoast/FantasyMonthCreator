<script lang="ts">
  import CreatorBody from "$lib/components/CreatorBody.svelte";
  import MonthListing from "$lib/components/MonthListing.svelte";
  import YearSlider from "$lib/components/YearSlider.svelte";
  import type { Month } from "$lib/types/month";

  let selectedYear = $state(0);
  let monthCollection = $state<Month[]>([]);

  function saveMonthEntry(addedMonth: Month) {
    monthCollection = [...monthCollection, addedMonth];
  }

  function removeMonthEntry(indexToRemove: number) {
    monthCollection = monthCollection.filter((_, index) => index !== indexToRemove);
  }
</script>

<div class="mx-auto grid max-w-5xl grid-cols-1 gap-6 lg:grid-cols-2">
  <section class="card bg-base-100 shadow-sm">
    <div class="card-body space-y-4">
      <h2 class="card-title">Creator</h2>
      <YearSlider bind:year={selectedYear} />
      <div class="divider my-0"></div>
      <CreatorBody onSave={saveMonthEntry} />
    </div>
  </section>

  <section class="card bg-base-100 shadow-sm">
    <div class="card-body space-y-4">
      <h2 class="card-title">Year {selectedYear}</h2>
      <MonthListing months={monthCollection} onRemove={removeMonthEntry} />
    </div>
    <div class="card-actions justify-end px-6 pb-6">
      <button class="btn btn-primary" disabled={monthCollection.length === 0}>Export</button>
    </div>
  </section>
</div>
