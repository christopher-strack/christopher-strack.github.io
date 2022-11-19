<template>
  <Line class="chart" :chart-data="data" />
</template>

<script lang="ts">
import { Chart, registerables } from "chart.js";
Chart.register(...registerables);
</script>

<script setup lang="ts">
import { computed } from "vue";
import { Line } from "vue-chartjs";
import { ChartData, ChartOptions } from "chart.js";

const data = computed<ChartData<"line">>(() => ({
  labels: ["a", "b", "c"],
  datasets: [
    {
      label: "values",
      data: [0, 1, 2],
      borderColor: "cyan",
      borderWidth: 1,
      fill: false,
      stepped: true,
    },
  ],
}));
</script>
