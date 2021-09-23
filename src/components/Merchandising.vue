<template>
    <div class="products">
        <div class="jumbotron">
            <img :src="require(`@/${pathImg[0].path}`)" :alt="pathImg[0].alt" />
        </div>
        <div class="current-series">
            <span class="title">CURRENT SERIES</span>
        </div>

       
            <div class="dc-products" style="color: white">
                
                <div v-for="(product, index) in products" :key="index">
                    <ProductCard  :prod="product" />
                </div>
            </div>
      
    </div>
</template>

<script>
    import dataProducts from '@/assets/data/dc-comics.js'
    import pathImg from "@/assets/data/PathImg.js";
    import ProductCard from '@/components/ProductCard.vue'
    export default {
        name: "Merchandising",
        components: {
            ProductCard,
        },
        data() {
            return {
                products: dataProducts,
                pathImg: pathImg,
            };
        },
    };
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    @import "./style/general";

    .jumbotron {
        @include img("jumbotron");
    }

    .products {
        position: relative;
        background-color: $background-box-products;
    }

    .current-series {

        height: 2.5em;
        width: max-content;
        position: absolute;
        /* bottom: 0px;
  left: 19em; */
        top: 0;
        left: 0;
        @include center(vertical);
        background-color: blue;
        padding: 0em 1em;
        color: $text-light;
        font-size: 1rem;
        font-weight: 600;
    }


    .dc-products {
        width:80%;
        margin: 0 auto;
        display: grid;
        align-items: center;
        grid-template-columns: repeat(6, 1fr);
        grid-template-rows: repeat(2, 1fr);
         gap: em(20) em(20);
        /* grid-column-gap: 20px;
        grid-row-gap: 0px; */
    }
</style>