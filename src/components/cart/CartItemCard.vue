<template>
    <div class="cart-item-card">
        <div class="header">
            <h3>{{ product.name }}</h3>
            <h4>In Cart: {{ product.quantity }}</h4>
            <h4>Total Cost: {{ item_cost.toFixed(2) }}</h4>
        </div>

        <p>{{ description }}</p>
    </div>
</template>

<script>
export default {
    props: ['product'],
    computed: {
        description() {
            return this.product.description.substring(0, 120)
        },
        item_cost() {
            return this.product.price * this.product.quantity
        }
    }
}
</script>

<style lang="scss">
    .cart-item-card{
        width: 90%;
        margin: auto;
        margin-top: 2%;
        margin-bottom: 2%;
        padding: 10px;
        background-color: #fff;
        box-shadow: 0 0 2px rgb(148, 148, 148);
        border-radius: 5px;
        padding: 10px;
        text-align: left;

        .header{
            display: flex;
            justify-content: space-around;
        }

        &:hover{
            box-shadow: 0 0 2px #1a202c;
        }
    }
</style>