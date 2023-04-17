<script lang="ts">
  import { onMount, onDestroy, createEventDispatcher } from 'svelte';
  import type { ApexOptions } from 'apexcharts';

  const dispatch = createEventDispatcher();

  let chartNode: HTMLElement, chart: any;
  export let options: ApexOptions;

  onMount(async () => {
    const ApexCharts = (await import('apexcharts')).default;
    chart = new ApexCharts(chartNode, options);
    chart.render();
  });

  $: if (chart && options) chart.updateOptions(options);

  onDestroy(() => {
    if (chart) chart.destroy();
  });
</script>

<div bind:this={chartNode} />
