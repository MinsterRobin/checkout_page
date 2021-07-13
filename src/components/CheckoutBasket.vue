<template>
    <div class="checkout-basket-layout">
        <div class="products-layout">
            <div v-for="product in products" :key="product.id">
                <BasketProduct
                        v-bind:product-photo="product.productPhoto"
                        v-bind:productName="product.productName"
                        v-bind:prize-actual="product.prizeActual"
                        v-bind:prize-old="product.prizeOld"/>
            </div>
        </div>
        <div class="prizes-total-layout">
            <hr>
            <div class="prize-total-line">
                <p>Shipping</p>
                <p>$19</p>
            </div>
            <hr>
            <div class="prize-total-line">
                <p class="prize-total-label">Total</p>
                <p class="">$148.98</p>
            </div>
        </div>
    </div>
</template>

<script>
    import BasketProduct from "@/components/BasketProduct";
    export default {
        name: "CheckoutBasket",
        components: {BasketProduct},
        data() {
            return {
                products: [
                    {
                        productPhoto: "photo1",
                        productName: "Vintage Backbag",
                        prizeActual: 54.99,
                        prizeOld: 74.99
                    },
                    {
                        productPhoto: "photo2",
                        productName: "Levi Shoes",
                        prizeActual: 74.99,
                        prizeOld: 124.99
                    }
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "../styles/breakpoints";
    @import "../styles/variables";

    .checkout-basket-layout {
        padding: 30px;
        max-width: max-content;
        width: auto;

        display: flex;
        flex-direction: column;
        background-color: $color-gray-6;
    }

    .products-layout {
        display: flex;
        flex-direction: column;
        row-gap: 30px;
    }

    .prizes-total-layout {
        margin-top: 90px;
        display: flex;
        flex-direction: column;
        row-gap: 8px;

        font-family: $font-family-primary;
        font-weight: 600;
        color: $color-gray-1;
    }

    hr {
        border: solid 1px #BDBDBD;
    }

    .prize-total-line {
        display: flex;
        justify-content: space-between;
    }

</style>