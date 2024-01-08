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
  <div>
    <BarChart :chart-data="chartData8" :options="chartOptions" />
  </div>
  <div>
    <LineChart :chart-data="chartData9" :options="chartOptions" />
  </div>
  <div>
    <LineChart :chart-data="chartData10" :options="chartOptions2" />
  </div>
</template>

<script setup>
import {ref} from 'vue';
import {BarChart, BubbleChart, DoughnutChart, LineChart, PieChart, PolarAreaChart, ScatterChart} from 'vue-chart-3';
import {Chart, registerables, CategoryScale, LinearScale, PointElement, LineElement, Title, Tooltip, Legend} from 'chart.js';
import 'chartjs-adapter-date-fns';

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

const chartData8 = ref({
  labels: ['January', 'February', 'March', 'April', 'May'],
  datasets: [
    {
      label: 'Bar Dataset',
      data: [10, 20, 30, 40, 50],
      backgroundColor: 'rgba(255, 99, 132, 0.5)',
      // 棒グラフを指定
      type: 'bar'
    },
    {
      label: 'Line Dataset',
      data: [50, 40, 30, 20, 10],
      borderColor: 'rgb(54, 162, 235)',
      // 折れ線グラフを指定
      type: 'line'
    }
  ]
});

const chartData9 = ref({
  labels: ['January', 'February', 'March', 'April', 'May'],
  datasets: [
    {
      label: 'My First dataset',
      data: [65, 59, 80, 81, 56],
      fill: false,
      borderColor: 'rgb(75, 192, 192)',
      tension: 0.4  // 曲線の強さを設定
    }
  ]
});

const chartData10 = ref({
  labels: ['2023/10/01', '2024/01/01', '2024/04/01', '2024/07/01', '2024/10/01'],
  datasets: [
    {
      label: '種目1',
      data: [6000, 6000, 6000, 6000, 6000],
      borderColor: 'blue',
      backgroundColor: 'rgba(0, 0, 255, 0.5)',
      tension: 0.1
    },
    {
      label: '種目2',
      data: [4000, 4500, 5000, 5500, 6000],
      borderColor: 'red',
      backgroundColor: 'rgba(255, 0, 0, 0.5)',
      tension: 0.1
    },
    {
      label: '種目3',
      data: [2000, 2400, 2800, 3200, 3600],
      borderColor: 'orange',
      backgroundColor: 'rgba(255, 165, 0, 0.5)',
      tension: 0.1
    }
  ]
});

// チャートオプションの設定
const chartOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
});

const chartOptions2 = ref({
  responsive: true,
  maintainAspectRatio: false,
  scales: {
    x: {
      type: 'time',
      time: {
        parser: 'yyyy/MM/dd',
        tooltipFormat: 'll'
      },
      title: {
        display: true,
        text: '日付'
      }
    },
    y: {
      title: {
        display: true,
        text: '値'
      }
    }
  },
  plugins: {
    legend: {
      display: true,
      position: 'top',
    },
    title: {
      display: true,
      text: 'フォロワー推移'
    }
  }
});
</script>
