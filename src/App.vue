<template>
  <div>
    <BarChart :chart-data="chartData1" :options="chartOptions"/>
  </div>
  <div>
    <LineChart :chart-data="chartData2" :options="chartOptions"/>
  </div>
  <div>
    <DoughnutChart :chart-data="chartData3" :options="chartOptions"/>
  </div>
  <div>
    <PieChart :chart-data="chartData4" :options="chartOptions"/>
  </div>
  <div>
    <PolarAreaChart :chart-data="chartData5" :options="chartOptions"/>
  </div>
  <div>
    <BubbleChart :chart-data="chartData6" :options="chartOptions"/>
  </div>
  <div>
    <ScatterChart :chart-data="chartData7" :options="chartOptions"/>
  </div>
</template>

<script setup>
import {ref} from 'vue';
import {BarChart, BubbleChart, DoughnutChart, LineChart, PieChart, PolarAreaChart, ScatterChart} from 'vue-chart-3';
import {Chart, registerables} from 'chart.js';

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

const chartData4 = ref({
  labels: ['Red', 'Green', 'Blue'],
  datasets: [
    {
      data: [300, 50, 100],
      backgroundColor: ['red', 'green', 'blue'],
    },
  ],
});

const chartData5 = ref({
  labels: ['Red', 'Green', 'Blue', 'Yellow', 'Purple'],
  datasets: [
    {
      label: 'My First Dataset',
      data: [11, 16, 7, 3, 14],
      backgroundColor: ['red', 'green', 'blue', 'yellow', 'purple'],
    },
  ],
});

const chartData6 = ref({
  datasets: [
    {
      label: 'First Dataset',
      data: [
        {x: 20, y: 30, r: 15},
        {x: 40, y: 10, r: 10},
      ],
      backgroundColor: 'rgb(255, 99, 132)',
    },
  ],
});

const chartData7 = ref({
  datasets: [
    {
      label: 'Scatter Dataset',
      data: [
        {x: -10, y: 0},
        {x: 0, y: 10},
        {x: 10, y: 5},
      ],
      backgroundColor: 'rgb(255, 99, 132)',
    },
  ],
});

// チャートオプションの設定
const chartOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
});
</script>
