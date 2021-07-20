<template>
    <div class="page-layout">
        <PageTitle title="Checkout"/>
        <div class="content-layout">
            <form class="form-layout" v-on:submit="onSubmit">

                <div class="form-subsection-layout">
                    <p class="form-subsection-title">Contact information</p>
                    <FormInput
                        label="E-mail"
                        type="email" id="email"
                        placeholder="Enter your email..."
                        icon="mail"
                    />

                    <FormInput
                        label="Phone"
                        type="tel" id="phone"
                        placeholder="Enter your phone..."
                        icon="phone"
                    />
                </div>

                <div class="form-subsection-layout">
                    <p class="form-subsection-title">Shipping address</p>
                    <FormInput
                        label="Full name"
                        type="text" id="fullname"
                        placeholder="Your full name.."
                        icon="pp"
                    />

                    <FormInput
                        label="Address"
                        type="text" id="address"
                        placeholder="Your address.."
                        icon="home"
                    />

                    <FormInput
                        label="City"
                        type="text" id="city"
                        placeholder="Your city.."
                        icon="city"
                    />
                    <div class="form-inputs-container">
                        <FormSelect
                            label="Country"
                            id="country"
                            icon="world"
                            placeholder="Your country"
                            v-bind:options="['France', 'Germany', 'Italy']"
                        />

                        <FormInput
                            label="Postal code"
                            type="text" id="postal"
                            pattern="[0-9]{5}"
                            placeholder="Your postal code.."
                            icon="postal"
                        />
                    </div>
                    <FormSaveCheckbox/>
                </div>

                <input type="submit" value="Continue" class="submit-button">
            </form>
            <CheckoutBasket class="checkout-basket-container" v-bind:products="products" v-bind:shipping="1900"/>
        </div>
        <Footer/>
    </div>
</template>

<script>
    import PageTitle from "@/components/PageTitle";
    import FormInput from "@/components/FormInput";
    import FormSaveCheckbox from "@/components/FormSaveCheckbox";
    import CheckoutBasket from "@/components/CheckoutBasket";
    import FormSelect from "@/components/FormSelect";
    import Footer from "@/components/Footer";

    export default {
        name: "Index",
        components: {Footer, FormSelect, CheckoutBasket, FormSaveCheckbox, FormInput, PageTitle},
        methods: {
            onSubmit : function () {
                alert("the form was sent successfully");
            }
        },
        data() {
            return {
                products: [
                    {
                        productPhoto: "photo1",
                        productName: "Vintage Backbag",
                        prizeActual: 5499,
                        prizeOld: 7499,
                        prizeUnitActual: 5499,
                        prizeUnitOld: 7499,
                        quantity: 1
                    },
                    {
                        productPhoto: "photo2",
                        productName: "Levi Shoes",
                        prizeActual: 7499,
                        prizeOld: 12499,
                        prizeUnitActual: 7499,
                        prizeUnitOld: 12499,
                        quantity: 1
                    }
                ]
            }
        },
    }
</script>

<style lang="scss" scoped>
    @import "../../styles/breakpoints";
    @import "../../styles/variables";

    .page-layout {
        min-height: 100vh;
        min-width: 250px;
        width: 100%;
        max-width: 1480px;
        padding: $padding-large;
        margin: auto;

        display: flex;
        flex-direction: column;

        background-color: $color-background;

        @include breakpoint('s') {
            padding: $padding-small;
        }
    }

    .content-layout {
        display: flex;
        justify-content: space-between;
        column-gap: 50px;
        row-gap: 40px;

        @include breakpoint('s') {
            flex-direction: column-reverse;
            align-items: center;
        }
    }

    .form-layout {
        flex: 2;

        max-width: max-content;
        width: 100%;
        min-width: min-content;

        display: flex;
        flex-direction: column;
        row-gap: 55px;
    }

    .form-subsection-layout {
        display: flex;
        flex-direction: column;
        row-gap: 20px;
    }

    .form-subsection-title {
        font-family: $font-family-primary;
        font-size: $font-size-medium;
        font-weight: 600;
        color: $color-gray-1;

        @include breakpoint('s') {
            font-size: $font-size-small;
        }
    }

    .form-inputs-container {
        display: flex;
        flex-wrap: wrap;
        width: 100%;
        justify-content: space-between;
        column-gap: 4vw;
        row-gap: 20px;
    }

    .submit-button {
        align-self: flex-end;

        width: 166px;
        padding: 17px 45px;
        background-color: $color-main;
        color: $color-background;
        border: none;
        border-radius: 12px;

        font-family: $font-family-primary;
        font-size: $font-size-regular;
        font-weight: 600;
    }

    .checkout-basket-container {
        flex: 1;
        max-width: max-content;
        width: 100%;
        height: max-content;
        border-radius: 12px;
    }

    .checkout-basket-container, .form-layout {
        @include breakpoint('s') {
            max-width: unset;
        }
    }
</style>