<template>
  <line-chart/>
  <pie-chart/>
  <reactive-chart/>
</template>

<script>
import LineChart from '@/components/chart/lineChart/LineChart.vue'
import PieChart from '@/components/chart/pieChart/PieChart.vue'
import ReactiveChart from '../components/chart/reactiveChart/ReactiveChart.vue'
export default {
	components: { LineChart,PieChart, ReactiveChart },

}
</script>

<style>

</style>