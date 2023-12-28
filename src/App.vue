<template>
  <v-card>
    <v-card-title>My Bar Chart</v-card-title>
    <v-card-text>
      <BarChart />
    </v-card-text>
  </v-card>
</template>

<script>
import BarChart from '@/components/BarChart.vue';

export default {
  components: {
    BarChart
  }
}
</script>