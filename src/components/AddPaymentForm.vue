<template>
  <div>
    <div class="addPayments">
      <input placeholder="Value" v-model="value">
      <input placeholder="Category" v-model="category">
      <input placeholder="Date" v-model="date">
      <button @click="onSaveClick">Save</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      value: '',
      category: '',
      date: '',
    }
  },
  methods: {
    onSaveClick() {
      const data = {
        value: +this.value,
        category: this.category,
        date: this.date,
      }
      this.$emit('addNewPayment', data)
    },
  }
}

</script>

<style lang="css">
.addPayments {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 10px 0;
}

input {
  width: 220px;
  margin: 5px 0;
  padding: 5px;
  box-sizing: border-box;
}

button {
  width: 220px;
  margin: 5px 0;
  padding: 5px;
  box-sizing: border-box;
}
</style>