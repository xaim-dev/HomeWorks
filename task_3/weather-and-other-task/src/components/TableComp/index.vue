<template>
    <div>
        <table v-for="product in tableListData" class="products__table"
               :key="product.id"
        >
        <tr>
            <td class="table__border">Назва продукту</td>
            <td class="table__border">{{product.name}}</td>
        </tr>
        <tr>
            <td class="table__border">Вартість</td>
            <td class="table__border">{{product.price}} грн</td>
        </tr>
        <tr>
            <td class="table__border">ПДВ</td>
            <td class="table__border">{{product.pdv}} %</td>
        </tr>
        <tr>
            <td class="table__border">До оплати</td>
            <td class="table__border">{{((product.price / 100) * product.pdv) + product.price}}</td>
        </tr>
        </table>
    </div>
</template>

<script>
    export default {
        name: 'TableComp',

        props: {
            tableListData: {
                type: Array,
                default: () => [],
            },
        },
    }
</script>

<style lang="css" scoped>
.products__table {
    border: 2px solid #000;
    border-radius: 5px;
    margin-bottom: 10px;
    font-family: 'Comfortaa', cursive;
    font-weight: 400;
    font-size: 18px;
    background-color: grey;
}
.table__border {
    border: 2px solid #000;
    border-radius: 5px;
    background-color: #fff;
}
</style>