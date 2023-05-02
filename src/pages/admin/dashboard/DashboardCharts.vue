<template>
  <div class="row row-equal">
    <div class="flex xs12 lg6 xl6">
      <va-card>
        <va-card-content>
          <va-chart class="chart" :data="lineData" type="line" />
        </va-card-content>
      </va-card>
    </div>

    <div class="flex xs12 sm6 md6 lg3 xl3">
      <va-card class="d-flex">
        <va-card-content>
          <va-chart ref="doughnutChart" class="chart chart--donut" :data="circleData" type="doughnut" />
        </va-card-content>
      </va-card>
    </div>

    <div class="flex xs12 sm6 md6 lg3 xl3">
      <dashboard-contributors-chart />
    </div>
  </div>
</template>

<script setup lang="ts">
  import { ref } from 'vue'
  import VaChart from '../../../components/va-charts/VaChart.vue'
  import DashboardContributorsChart from './DashboardContributorsList.vue'

  const doughnutChart = ref()

  const lineData = ref({
    labels: ['2021.01.02', 'February', 'March', 'April', 'May'],
    datasets: [{ label: '멤버수', backgroundColor: '#f87979', data: [18, 92, 18, 64, 95] }],
  })

  const circleData = ref({
    labels: ['남자', '여자'],
    datasets: [{ backgroundColor: ['#158DE3', '#E42222'], data: [8000, 5267] }],
  })
</script>

<style scoped>
  .chart {
    height: 400px;
  }
</style>
