<template>
    <div>
        <router-link class="button is-success mt-5"> Add New </router-link>
        <table class="table is-striped is-bordered mt-2 is-fullwidth">
            <thead>
                <tr>
                    <th> Product Name </th>
                    <th> Price </th>
                    <th class="has-text-centered"> Actions </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="product of products" :key="product.prodID">
                    <td>{{ product.prodName }}</td>
                    <td> {{ product.amount }}</td>
                    <td class="has-text-centered">
                        <router-link class="button is-info is-small"> {{Edit}} </router-link>
                        <a class="button is-danger is-small" @click="deleteProduct(product.prodID)"> Delete </a>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    // Import axios
import axios from 'axios';

export default {
    name: "ProductList",

    data() {
        return { 
            products: [],
        };
    },

    created() {
        this.getProducts();
    },

    methods: {
            // Get all Products
        async getProducts() {
            try {
                const response = await axios.get("http://localhost:5000/products");
                this.products = response.data;
            } catch (err) {
                console.log(err);
            }
        },

            // Delete product
        async  deleteProduct(id) {
            try{
                await axios.delete(`http://localhost:5000/products/${id}`);
                this.getProducts();
            } catch (err) {
                console.log(err);
            }
        },
    },
}
</script>