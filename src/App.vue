<template>
  <div id="app">
    <header>
      <h1 class="app_title">My personal costs</h1>
    </header>
    <main>
      <PaymentsDisplay :items="paymentsList"></PaymentsDisplay>
      <AddNewCost @addVisible="clicked"></AddNewCost>
      <AddPaymentFormVue v-if="elVisible" @addNewPayment="addNewPayment"></AddPaymentFormVue>
    </main>
  </div>
</template>

<script>
import PaymentsDisplay from './components/PaymentsDisplay.vue'
import AddPaymentFormVue from './components/AddPaymentForm.vue'
import AddNewCost from './components/Button.vue'

export default {
  components: {
    PaymentsDisplay,
    AddPaymentFormVue,
    AddNewCost,
  },
  data() {
    return {
      paymentsList: [],
      elVisible: false,
    }
  },
  methods: {
    fetchData() {
      return [
        { id: 1, date: "20.09.2022", category: "food", value: 1582 },
        { id: 2, date: "15.09.2022", category: "transport", value: 245 },
        { id: 3, date: "22.09.2022", category: "healthcare", value: 780 },
        { id: 4, date: "22.09.2022", category: "healthcare", value: 780 },
      ]
    },
    addNewPayment(data) {
      this.paymentsList = [...this.paymentsList, data]
    },
    clicked() {
      console.log('Вы отобразили форму')
      this.elVisible = !this.elVisible;
    }
  },
  created() {
    this.paymentsList = this.fetchData()
  },
  computed: {

  },
}
</script>

<style lang="css">
.app_title {
  text-align: center;
}

main {
  max-width: 680px;
  margin: 0 auto;
}
</style>
