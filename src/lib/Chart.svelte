<script lang="ts">
  import { onMount, onDestroy } from "svelte";
  import type { ApexOptions } from "apexcharts";

  let chartNode = $state<HTMLElement>(),
    chart: any = $state();

  let { options } = $props<{ options: ApexOptions }>();

  onMount(async () => {
    const ApexCharts = (await import("apexcharts")).default;
    chart = new ApexCharts(chartNode, options);
    chart.render();
  });

  $effect(() => {
    if (chart && options) chart.updateOptions(options);
  });

  onDestroy(() => {
    if (chart) chart.destroy();
  });
</script>

<div bind:this={chartNode}></div>
