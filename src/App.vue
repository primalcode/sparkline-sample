<template>
  <div>
    <BarChart :chart-data="chartData1" :options="chartOptions" />
  </div>
  <div>
    <LineChart :chart-data="chartData2" :options="chartOptions" />
  </div>
  <div>
    <DoughnutChart :chart-data="chartData3" :options="chartOptions" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { BarChart, LineChart, DoughnutChart } from 'vue-chart-3';
import { Chart, registerables } from 'chart.js';
Chart.register(...registerables);

// チャートデータの設定
const chartData1 = ref({
  labels: ['January', 'February', 'March', 'April', 'May'],
  datasets: [
    {
      label: 'My First dataset',
      backgroundColor: '#f87979',
      data: [40, 20, 12, 39, 10],
    },
  ],
});

const chartData2 = ref({
  labels: ['January', 'February', 'March', 'April', 'May'],
  datasets: [
    {
      label: 'Dataset 1',
      borderColor: 'rgb(255, 99, 132)',
      backgroundColor: 'rgba(255, 99, 132, 0.5)',
      data: [0, 20, 40, 50, 60, 70],
    },
  ],
});

const chartData3 = ref({
  labels: ['Red', 'Blue', 'Yellow'],
  datasets: [
    {
      label: 'My First Dataset3',
      data: [300, 50, 100],
      backgroundColor: ['red', 'blue', 'yellow'],
    },
  ],
});

// チャートオプションの設定
const chartOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
});
</script>
