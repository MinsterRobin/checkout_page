<template>
    <div class="page-layout">
        <PageTitle title="Checkout"/>
        <form class="form-layout" v-on:submit="onSubmit">

            <FormInput
                    label="E-mail"
                    type="email" id="email"
                    placeholder="Enter your email..."
            />

            <FormInput
                    label="Phone"
                    type="tel" id="phone"
                    placeholder="Enter your phone..."
            />

            <FormInput
                    label="Full name"
                    type="text" id="fullname"
                    placeholder="Your full name.."
            />

            <FormInput
                    label="Address"
                    type="text" id="address"
                    placeholder="Your address.."
            />

            <FormInput
                    label="City"
                    type="text" id="city"
                    placeholder="Your city.."
            />

            <label for="country">Country</label>
            <select name="country" id="country" required>
                <option>France</option>
                <option>Germany</option>
                <option>Italy</option>
            </select>

            <FormInput
                    label="Postal code"
                    type="text" id="postal"
                    pattern="[0-9]{5}"
                    placeholder="Your postal code.."
            />

            <input type="submit" value="Continue">
        </form>
    </div>
</template>

<script>
    import PageTitle from "@/components/PageTitle";
    import FormInput from "@/components/FormInput";
    export default {
        name: "Index",
        components: {FormInput, PageTitle},
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
        display: flex;
        flex-direction: column;
    }
</style>