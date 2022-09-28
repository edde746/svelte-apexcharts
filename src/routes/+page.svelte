<script>
  import Chart from '$lib';
</script>

<div>
  <h1>svelte-apexcharts demo</h1>
  <Chart
    options={{
      chart: {
        type: 'bar',
      },
      series: [
        {
          name: 'sales',
          data: [30, 40, 35, 50, 49, 60, 70, 91, 125],
        },
      ],
      xaxis: {
        categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999],
      },
    }}
  />
</div>

<style>
  div {
    max-width: 24rem;
    margin: 12rem auto;
    text-align: center;
    font: 1em sans-serif;
  }
</style>
