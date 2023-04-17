# svelte-apexcharts

A Svelte wrapper for the popular ApexCharts library. Easily create interactive and responsive charts for your Svelte projects.

## Installation

Install the package using pnpm:

```bash
pnpm add @edde746/svelte-apexcharts
```

Alternatively, use npm or yarn:

```bash
npm install @edde746/svelte-apexcharts
```

```bash
yarn add @edde746/svelte-apexcharts
```

## Usage

Import the `Chart` component from the package and use it in your Svelte components:

```svelte
<script>
  import Chart from '@edde746/svelte-apexcharts';
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
```

## Configuration

You can pass any valid [ApexCharts options](https://apexcharts.com/docs/options/) to the `options` prop of the `Chart` component. For example, to create a line chart, you can update the `chart.type` property:

```svelte
<Chart
  options={{
    chart: {
      type: 'line',
    },
    // ...other options
  }}
/>
```

## Updating Data

To update the chart data, simply update the `options` prop with the new data. The chart will automatically update to reflect the changes:

```svelte
<script>
  let chartOptions = {
    // ...initial options
  };

  function updateData() {
    chartOptions = {
      ...chartOptions,
      series: [
        {
          name: 'sales',
          data: [45, 60, 55, 70, 69, 80, 90, 111, 140],
        },
      ],
    };
  }
</script>

<button on:click={updateData}>Update Data</button>
<Chart options={chartOptions} />
```

## License

This project is licensed under the GPL v3.0 License - see the [LICENSE](LICENSE) file for details.