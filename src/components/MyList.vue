<template>
    <!-- <ul class="paymentsList">
        <div class="paymentsList_title">
            <span>#</span>
            <span>Date</span>
            <span>Category</span>
            <span>Value</span>
        </div>
        <li v-for="payment in list" :key="payment.id" class="paymentsList_item">
            <span class="row">{{ item }}</span>
        </li>
    </ul> -->

    <table class="costs-list">
        <thead>
            <tr class="costs-list__title">
                <th>#</th>
                <th>Date</th>
                <th>Category</th>
                <th>Value</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="cost in list" :key="cost.id" class="costs-list__item">
                <td>{{ cost.id }}</td>
                <td>{{ cost.date }}</td>
                <td>{{ cost.category }}</td>
                <td>{{ cost.value }}</td>
                <td>
                    <span :class="[record.typeClass]" class="white-text badge">{{ record.typeText }}</span>
                </td>
                <td>
                    <button v-tooltip="'Посмотреть запись'" class="btn-small btn"
                        @click="$router.push('/detail/' + record.id)">
                        <i class="material-icons">open_in_new</i>
                    </button>
                </td>
            </tr>
        </tbody>
    </table>
</template>

<script>
export default {
    name: 'MyList',
    props: {
        list: Array,
    },
};
</script>

<style>

</style>