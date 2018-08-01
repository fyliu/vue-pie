<template>
  <div class="hello">
    <pie-chart :data="categoryData"></pie-chart>
    <!--<line-chart :data="chartData"></line-chart>-->
    <hr>
    <div>
      {{ categoryData }}
      <br>
      Chart Name: <input type="text" v-model="chartName">
    </div>
    <div>
      Category: <input type="text" v-model="category_1_name">
      Percentage: <input type="text" v-model="category_1_value"><br>
      Category: <input type="text" v-model="category_2_name">
      Percentage: <input type="text" v-model="category_2_value"><br>
      Category: <input type="text" v-model="category_3_name">
      Percentage: <input type="text" v-model="category_3_value"><br>
      Category: <input type="text" v-model="category_4_name">
      Percentage: <input type="text" v-model="category_4_value"><br>
      Category: <input type="text" v-model="category_5_name">
      Percentage: <input type="text" v-model="category_5_value">
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
  </div>
</template>

<script>


export default {
  name: 'HelloWorld',
  data () {
    return {
      chartName: '',
      category_1_name: 'Blueberry',
      category_1_value: '44',
      category_2_name: 'Strawberry',
      category_2_value: '56',
      category_3_name: 'Banana',
      category_3_value: '',
      category_4_name: 'Orange',
      category_4_value: '',
      category_5_name: 'Pineapple',
      category_5_value: '',
      //chartData: [["Jan", 4], ["Feb", 2], ["Mar", 10], ["Apr", 5], ["May", 3]],
      //chartDataPie: [['Blueberry', 44], ['Strawberry', 23]]
      //chartDataPie: {'Blueberry': 44, 'Strawberry': 23}
    }
  },
  computed: {
    categoryData: function() {
      //return {'Blueberry': 44, 'Strawberry': 23}
      return { [this.category_1_name] : this.category_1_value,
        [this.category_2_name] : this.category_2_value ,
        [this.category_3_name] : this.category_3_value ,
        [this.category_4_name] : this.category_4_value ,
        [this.category_5_name] : this.category_5_value }
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
