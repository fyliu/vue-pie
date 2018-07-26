<template>
  <div class="hello">
    <pie-chart :data="chartDataPie"></pie-chart>
    <!--<line-chart :data="chartData"></line-chart>-->
    <hr>
    <div>
      Chart Name: <input type="text" v-model="chartName">
    </div>
    <div v-if="chartName">
      <ul>
        <li v-for='(value, key, index) in chartDataPie'>
          {{ key }}: {{ value }}: {{ index }}
        </li>
      </ul>
      <div v-for="(value, key, index) in chartDataPie">
        <input type="text" v-model="chartDataPie[key]">
        <input type="text" v-model="chartDataPie[index]">
      </div>
      <div v-for="d in chartDataPie">
        Input Value <span v-text="d[0]"></span>
        Input Value <span v-text="d[1]"></span>
      </div>
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
      category_1_name: 'blueberry',
      category_1_value: '44',
      category_2_name: '',
      category_2_value: '',
      category_3_name: '',
      category_3_value: '',
      category_4_name: '',
      category_4_value: '',
      category_5_name: '',
      category_5_value: '',
      chartData: [["Jan", 4], ["Feb", 2], ["Mar", 10], ["Apr", 5], ["May", 3]],
      //chartDataPie: [['Blueberry', 44], ['Strawberry', 23]]
      chartDataPie: {'Blueberry': 44, 'Strawberry': 23}
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
