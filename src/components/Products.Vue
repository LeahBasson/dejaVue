<template>
  <div class="container">
    
    <div class="row">
        <h2 class="display-2">Products</h2>
    </div>

    <div class="row">
        <div class="spinner-border mx-auto" role="status" v-if="!products.length">
        <span class="visually-hidden">Loading...</span>
        </div>
      </div>

    <div class="row gap-2">
        <Card v-for="product in products" :key="product.id">
            <template #cardHeader>
                <img :src="product.img_url" :alt="product.productName" class="img-fluid"/>
            </template>

            <template #cardBody>
                <p>id: {{ product.id }}</p>
                <p>{{ product.productName }}</p>
                <p>Amount: R{{ product.Amount }}</p>
            </template>
        </Card>
    </div>

  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
    name: "Products",
    components: {
      Card
    },

    data() {
        return {
            products: [
                {
                    id: 1,
                    productName: "Gemstone",
                    category: "Ring",
                    Material: "Gold",
                    Amount: 1000,
                    img_url: "https://leahbasson.github.io/MyImages/jsProject/circle1.jpg"
                },
                {
                    id: 2,
                    productName: "Chunky Silver",
                    category: "Bracelet",
                    Material: "Silver",
                    Amount: 300,
                    img_url: "https://leahbasson.github.io/MyImages/jsProject/circle2.png"
                },
                {
                    id: 3,
                    productName: "Chain Necklace",
                    category: "Necklace",
                    Material: "Gold",
                    Amount: 600,
                    img_url: "https://leahbasson.github.io/MyImages/jsProject/circle3.jpg"
                },
                {
                    id: 4,
                    productName: "Pear Shaped Pearls",
                    category: "Earrings",
                    Material: "Pearls, Gold",
                    Amount: 300,
                    img_url: "https://leahbasson.github.io/MyImages/jsProject/circle4.jpg"
                }
            ]
        }
    }

}
</script>

<style>

</style>