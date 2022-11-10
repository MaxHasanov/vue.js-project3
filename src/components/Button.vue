<template>
  <div class="btn-wrap">
    <button @click="click" class="visible-btn">ADD NEW COST +</button>
  </div>
</template>

<script>
export default {
  name: 'AddNewCost',
  methods: {
    click() {
      this.$emit('addVisible')
    }
  }
}
</script>

<style>
.btn-wrap {
  display: flex;
  justify-content: center;
  margin-top: 15px;
}
</style>