<template>
  <div class="hello">
    <pie-chart :data="chartDataPie"></pie-chart>
    <!--<line-chart :data="chartData"></line-chart>-->
    <ul>
      <li v-for="d in chartDataPie">
        {{d[0]}} {{d[1]}}
      </li>
    </ul>
    <input type="text" v-model="chartDataPie[0][0]">
  </div>
</template>

<script>


export default {
  name: 'HelloWorld',
  data () {
    return {
      chartData: [["Jan", 4], ["Feb", 2], ["Mar", 10], ["Apr", 5], ["May", 3]],
      chartDataPie: [['Blueberry', 44], ['Strawberry', 23]]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
