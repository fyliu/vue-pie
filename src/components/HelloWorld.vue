<template>
  <div class="hello">
    <pie-chart :data="chartDataPie"></pie-chart>
    <!--<line-chart :data="chartData"></line-chart>-->
    <hr>
    <div>
      Chart Name: <input type="text" v-model="chartName">
    </div>
    <ul>
      <li v-for="d in chartDataPie">
        {{d[0]}} {{d[1]}}
      </li>
    </ul>
    <div v-for="d in chartDataPie">
      <input type="text" v-model="d[0]">
      <input type="text" v-model="d[1]">
    </div>
    <div v-for="d in chartDataPie">
      Input Value <span v-text="d[0]"></span>
      Input Value <span v-text="d[1]"></span>
    </div>
    <!--
    <div>
      <input type="text" v-model="d[1]">
    </div>
    <div>
      <input type="text" v-model="d[1]">
    </div>
    <div>
      <input type="text" v-model="d[1]">
    </div>
    -->
  </div>
</template>

<script>


export default {
  name: 'HelloWorld',
  data () {
    return {
      chartName: '',
      chartData: [["Jan", 4], ["Feb", 2], ["Mar", 10], ["Apr", 5], ["May", 3]],
      chartDataPie: [['Blueberry', 44], ['Strawberry', 23]]
      //chartDataPie: {'Blueberry': 44, 'Strawberry': 23}
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
