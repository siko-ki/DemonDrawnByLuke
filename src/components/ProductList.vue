<template>
    <div class="cart">
        <div class="items">
            <div class="item clearfix" v-for="product in products" :key="product.id">
                    <div class="item-details">
                        <item>{{product.name}}</item>
                        <p>{{product.country}}</p>
                    </div>
                    <br>
                <img :src="'/images/products/'+product.image" class="item-image" alt="">
                <div class="divider">
                    <div class ="addToCart">
                        <button class="auto" @click="AddToCart(product)" >Add to Cart</button>
                    </div>
                    <div class="item-price">
                        <h2>{{product.price}}</h2>
                    </div>
                </div>
            </div>
        </div>
        </div>
</template>
<script>
    export default {
        name: 'ProductList',
        props: {
            products: Array
        },
        methods: {
            AddToCart(product) {
                this.$root.$data.cart.push(product);
            }
        }
    }
</script>

<style scoped>
    .cart {
        margin-top: 100px;
        margin-left: 1em;
    }
    .cart-title {
        margin: 0.5em 0 0 0;
        font-weight: bold;
        text-transform: uppercase;
        text-align: center;
        padding: 0.75em;
        background: #35495E;
        color: #fff;
    }
    .cart-empty {
        text-align: center;
        margin: 4em 0 0 0;
        min-height: 300px;
    }

    .items {
        min-height: 300px;
    }
    .item {
        padding: 0.75em 0.5em;
        border-top: 1px solid #ddd;
        overflow-y: hidden;
        display: flex;
    }

    .item-image {
        float: left;
        height: 20%;
        width: 20%;

    }
    .item-details {
        float: right;
        width: 80%;
        padding-left: 0.75em;
        font-size: large;
        font-weight: bold;
    }

    .item-price {
        float: right;
        width: 80%;
        padding-left: 0.75em;
        font-size: 0.9em;
    }
    .addToCart {
        float: right;
        width: 80%;
        padding-left: 0.75em;
        font-size: 0.9em;
    }
</style>
