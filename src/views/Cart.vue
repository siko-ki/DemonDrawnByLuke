<template>
    <div class="cart">
        <p class="cart-title">Shopping Cart</p>
        <p class="cart-empty" v-if="this.$root.$data.cart && this.$root.$data.cart.length < 1"> You have an Empty Cart!</p>
            <div class="items" v-else>
                <div class="item clearfix" v-for="product in this.$root.$data.cart" :key="product.id">
                    <img :src="'/images/products/'+product.image" class="item-image" alt="">
                    <div class="item-details">
                        <item>{{product.name}}</item>
                        <p>{{product.country}}</p>
                    </div>

                    <div class="item-price">
                        <h2>{{product.price}}</h2>
                    </div>
                    <br>
                </div>
            </div>
    </div>
</template>

<style>
    .cart {
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
    }

    .item-price {
        float: right;
        width: 80%;
        padding-left: 0.75em;
        font-size: 0.9em;
    }
</style>