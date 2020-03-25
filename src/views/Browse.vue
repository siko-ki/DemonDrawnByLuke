<template>
    <div>
        <div class="pure-menu pure-menu-horizontal">
            <ul class="pure-menu-list">
                <li class="pure-menu-item"><a @click="select('Digital')" href="#" class="pure-menu-link">Digital</a>
                </li>
                <li class="pure-menu-item"><a @click="select('Digitized')" href="#" class="pure-menu-link">Digitized</a>
                </li>
                <li class="pure-menu-item"><a @click="select('Painted')" href="#" class="pure-menu-link">Painted</a>
                </li>
                <li class="pure-menu-item"><a @click="select('Original')" href="#" class="pure-menu-link">Original</a>
                </li>
            </ul>
        </div>
        <ProductList :products="products"/>
    </div>
</template>
<script>
    import ProductList from "../components/ProductList.vue"

    export default {
        name: 'Browse',
        components: {
            ProductList
        },
        data() {
            return {
                medium: '',
            }
        },
        computed: {
            products() {
                return this.$root.$data.products.filter(product => product.medium == this.medium);
            }
        },
        methods: {
            select(medium) {
                this.medium = medium;
            }
        }
    }
</script>