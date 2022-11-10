<template>
  <div class="payments-table">
    <ul class="payments-ul">
      <li>Date</li>
      <li>Category</li>
      <li>Value</li>
    </ul>
    <div class="item" v-for="(item, idx) in items" :key="idx">
      <div class="itms">{{ item.date }}</div>
      <div class="itms">{{ item.category }}</div>
      <div class="itms">{{ item.value }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['items'],
}
</script>

<style lang="css">
.payments-table {
  display: flex;
  flex-direction: column;
  background-color: antiquewhite;
  border-radius: 15px;
}

.item {
  display: flex;
  justify-content: space-evenly;
  padding: 5px 0;
  border: 2px solid gray;
  border-radius: 5px;
}

.payments-ul {
  display: flex;
  justify-content: space-evenly;
  list-style-type: none;
  font-weight: bold;
}
</style>