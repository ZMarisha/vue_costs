<template>
  <div id="app" class="container">
    <header>
      <div class="header">My personal costs</div>
    </header>
    <main>
      <button class="btn" @click="showForm">ADD NEW COST<span>+</span></button>
      <CostsForm @add-costs="addCosts" v-show="hidden"/>
      <CostsDisplay :costsList = "costsList" show/>
    </main>
  </div>
</template>

<script>
import CostsForm from './components/CostsForm.vue'
import CostsDisplay from './components/CostsDisplay.vue'

export default {
  name: 'App',
  components: {
    CostsForm,
    CostsDisplay
  },
  data: () => ({
    costsList: [],
    hidden: false,
    show: true
  }),
  methods: {
    fetchCostsData () {
      return [
        { id: 1, date: '12.05.2022', category: 'Food', value: 210 },
        { id: 2, date: '28.05.2022', category: 'Clothing', value: 1200 },
        { id: 3, date: '17.06.2022', category: 'Housing', value: 502 },
        { id: 4, date: '30.08.2022', category: 'Healthcare', value: 545 },
        { id: 5, date: '02.09.2022', category: 'Transport', value: 350 },
        { id: 6, date: '05.09.2022', category: 'Transport', value: 120 },
        { id: 7, date: '06.09.2022', category: 'Food', value: 1230 },
        { id: 8, date: '07.09.2022', category: 'Food', value: 1100 },
        { id: 9, date: '07.09.2022', category: 'Transport', value: 120 },
        { id: 10, date: '08.09.2022', category: 'Food', value: 1230 },
        { id: 11, date: '12.05.2022', category: 'Food', value: 210 },
        { id: 12, date: '28.05.2022', category: 'Clothing', value: 1200 },
        { id: 13, date: '17.06.2022', category: 'Housing', value: 502 },
        { id: 14, date: '30.08.2022', category: 'Healthcare', value: 545 },
        { id: 15, date: '02.09.2022', category: 'Transport', value: 350 },
        { id: 16, date: '05.09.2022', category: 'Transport', value: 120 },
        { id: 17, date: '06.09.2022', category: 'Food', value: 1230 },
        { id: 18, date: '07.09.2022', category: 'Food', value: 1100 },
        { id: 19, date: '07.09.2022', category: 'Transport', value: 120 }
      ]
    },
    addCosts (data) {
      this.costsList.push(data)
    },
    showForm () {
      this.hidden = !this.hidden
    }
  },
  created () {
    this.costsList = this.fetchCostsData()
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
* {
  margin: 0;
  padding: 0;
}
.container {
  margin: 0 auto;
  max-width: 1140px;
}
.header {
  font-size: 28px;
  font-weight: 600;
  color: black;
  margin-bottom: 90px;
}
.btn {
  height: 30px;
  width: 150px;
  background: #087936;
  color: white;
  text-align: center;
  margin-bottom: 15px;
  font-weight: 600;
}
.btn span {
  padding-left: 10px;
}
@media (max-width: 1024px) {
  .container {
    padding-left: 16px;
    padding-right: 16px;
  }
}
@media (min-width: 320px) and (max-width: 667px) {
  .container {
    padding-left: 8px;
    padding-right: 8px;
  }
  .header {
    font-size: 20px;
  }
}

</style>
