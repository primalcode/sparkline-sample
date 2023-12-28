<template>
  <div>
    <BarChart :chart-data="chartData" :options="chartOptions" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { BarChart } from 'vue-chart-3';
import { Chart, registerables } from 'chart.js';
Chart.register(...registerables);

// チャートデータの設定
const chartData = ref({
  labels: ['January', 'February', 'March', 'April', 'May'],
  datasets: [
    {
      label: 'My First dataset',
      backgroundColor: '#f87979',
      data: [40, 20, 12, 39, 10],
    },
  ],
});

// チャートオプションの設定
const chartOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
});
</script>
