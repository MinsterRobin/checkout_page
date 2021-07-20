<template>
    <div class="basket-product-layout">

        <img class="product-photo" v-bind:src="require('@/assets/' + productPhoto + '.png')" alt="Product photo">

        <div class="product-infos-layout">
            <div class="product-infos-sublayout">
                <p class="product-name">{{productName}}</p>

                <div class="product-prizes-container">
                    <p class="prize-actual">${{prizeActual / 100}}</p>
                    <p class="prize-old">${{prizeOld / 100}}</p>
                </div>
            </div>


            <div class="product-number-controller-layout">
                <button class="product-number-button" v-on:click="$emit('decrement', index)">-</button>
                <p class="product-number">{{quantity}}</p>
                <button class="product-number-button" v-on:click="$emit('increment', index)">+</button>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        name: "BasketProduct",
        props: {
            index: {
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
                required: false
            },
            productPhoto: {
                type: String,
                required: true
            },
            quantity: {
                type: Number,
                required: true
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "../styles/breakpoints";
    @import "../styles/variables";

    .basket-product-layout {
        width: 100%;
        display: flex;
        flex-wrap: wrap;

        gap: 20px;

        font-family: $font-family-primary;
        font-weight: 600;
    }

    .product-photo {
        flex: 1;
        max-width: 175px;
        min-width: 120px;
        height: auto;
        border-radius: 13px;
    }

    .product-name {
        font-size: $font-size-regular;
        color: $color-gray-4;

        @include breakpoint('s') {
            font-size: $font-size-very-small;
        }
    }

    .product-infos-layout {
        flex: 1;

        display: flex;
        flex-direction: column;
        height: auto;
        justify-content: space-between;
        gap: 20px;
    }

    .product-infos-sublayout {
        display: flex;
        flex-direction: column;
        gap: 10px;
    }

    .product-prizes-container {
        display: flex;
        align-items: center;

        column-gap: 14px;
    }

    .prize-actual {
        font-size: $font-size-regular;
        color: $color-main;

        @include breakpoint('s') {
            font-size: $font-size-small;
        }
    }

    .prize-old {
        font-size: $font-size-very-small;
        text-decoration-line: line-through;
        color: $color-gray-4;

        @include breakpoint('s') {
            font-size: $font-size-tiny;
        }
    }

    .product-number-controller-layout {
        border: 1px solid $color-gray-3;
        border-radius: 12px;

        display: flex;
        justify-content: space-between;

        padding: 15px 13px;
    }

    .product-number-button {
        border: none;
        border-radius: 4px;
        background-color: $color-gray-5;
        font-size: 16px;
        color: $color-gray-3;
        font-weight: 500;
        cursor: pointer;
    }

    .product-number-button:hover {
        background-color: #D0D0D0;
    }

    .product-number {
        font-size: $font-size-regular;
    }
</style>