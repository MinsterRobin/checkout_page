<template>
    <div class="checkout-basket-layout">
        <div class="products-layout">
            <div v-for="product in products" :key="product.index">
                <BasketProduct
                        v-bind:index="products.indexOf(product)"
                        v-bind:product-photo="product.productPhoto"
                        v-bind:productName="product.productName"
                        v-bind:prize-actual="product.prizeActual"
                        v-bind:prize-old="product.prizeOld"
                        v-bind:quantity="product.quantity"
                        v-on:increment="handleIncrement"
                        v-on:decrement="handleDecrement"
                />
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
                <p class="">${{totalBasketPrize}}</p>
            </div>
        </div>
    </div>
</template>

<script>
    import BasketProduct from "@/components/BasketProduct";
    export default {
        name: "CheckoutBasket",
        components: {BasketProduct},
        props: {
            products: {
                type: Array,
                required: true,

                productPhoto: {
                    type: String,
                    required: true
                },
                productName: {
                    type: String,
                    required: true
                },
                prizeActual: {
                    type: Number,
                    required: true
                },
                prizeOld: {
                    type: Number,
                    required: true
                },
                prizeUnitActual: {
                    type: Number,
                    required: true
                },
                prizeUnitOld: {
                    type: Number,
                    required: true
                },
                quantity: {
                    type: Number,
                    required: true
                }
            },
        },
        computed: {
            totalBasketPrize() {
                let totalPrize = 0;
                for (const product of this.products) {
                    totalPrize += product.prizeActual;
                }
                return totalPrize  / 100;
            }
        },
        methods: {
            handleIncrement(index) {
                this.products[index].prizeActual = this.products[index].prizeActual + this.products[index].prizeUnitActual;
                this.products[index].prizeOld =  this.products[index].prizeOld + this.products[index].prizeUnitOld;
                this.products[index].quantity += 1;
            },
            handleDecrement(index) {
                if (this.products[index].prizeActual !== 0) {
                    this.products[index].prizeActual =  this.products[index].prizeActual - this.products[index].prizeUnitActual;
                    this.products[index].prizeOld =  this.products[index].prizeOld - this.products[index].prizeUnitOld;
                    this.products[index].quantity -= 1;
                }
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