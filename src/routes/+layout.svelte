<script lang="ts">
  import "../app.css";
  import Navbar from "$lib/components/Navbar.svelte";
</script>

<div class="min-h-screen bg-base-200 text-base-content">
  <Navbar />
  <slot />
</div>
