<template>
    <div class="page-layout">
        <PageTitle title="Checkout"/>
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
<!--                    <label for="country">Country</label>-->
                    <FormInput
                            label="City"
                            type="text" id="city"
                            placeholder="Your city.."
                            icon="city"
                    />
<!--                    <select name="country" id="country" required>-->
<!--                        <option>France</option>-->
<!--                        <option>Germany</option>-->
<!--                        <option>Italy</option>-->
<!--                    </select>-->

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
        <CheckoutBasket/>
    </div>
</template>

<script>
    import PageTitle from "@/components/PageTitle";
    import FormInput from "@/components/FormInput";
    import FormSaveCheckbox from "@/components/FormSaveCheckbox";
    import CheckoutBasket from "@/components/CheckoutBasket";

    export default {
        name: "Index",
        components: {CheckoutBasket, FormSaveCheckbox, FormInput, PageTitle},
        methods: {
            onSubmit : function () {
                alert("OK");
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "../../styles/breakpoints";
    @import "../../styles/variables";

    .page-layout {
        min-height: 100vh;
        width: 100%;
        max-width: 1680px;
        padding: $padding-large;
        margin: auto;

        display: flex;
        flex-direction: column;

        background-color: $color-background;

        @include breakpoint('s') {
            padding: $padding-small;
        }
    }

    .form-layout {
        flex: 1;
        row-gap: 55px;
        display: flex;
        flex-direction: column;
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
        width: 100%;
        justify-content: space-between;
        column-gap: 4vw;
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
</style>