<template>
    <div class="form-input-layout">
        <FormLabel v-bind:label="label" v-bind:id="id">{{label}}</FormLabel>
        <div class="input-container">
            <img v-bind:src="require('@/assets/' + icon + '.svg')" alt="Input icon"/>
            <input
                    v-bind:type="type"
                    v-bind:pattern="pattern"
                    v-bind:name="id"
                    v-bind:id="id"
                    v-bind:placeholder="placeholder"
                    required
            >
        </div>
    </div>
</template>

<script>
    import FormLabel from "@/components/FormLabel";
    export default {
        name: "FormInput",
        components: {FormLabel},
        props: {
            label: String,
            type: {
                type: String,
                required: true
            },
            id: {
                type: String,
                required: true
            },
            placeholder: String,
            pattern: String,
            icon: {
                type: String,
                required: true
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "../styles/breakpoints";
    @import "../styles/variables";

    .form-input-layout {
        display: flex;
        flex-direction: column;
        row-gap: 6px;

        font-family: $font-family-primary;
        font-size: $font-size-very-small;
        font-weight: 600;
        width: 100%;
    }

    .input-container {
        position: relative;
        display: flex;
        align-items: center;
    }

    img {
        position: absolute;

        margin-left: 1rem;
    }

    input {
        font-family: $font-family-primary;
        font-weight: 600;
        font-size: $font-size-regular;
        line-height: 20px;
        padding-left: 3rem;
        width: 100%;

        height: 56px;
        border: 1px solid $color-gray-3;
        border-radius: 12px;

        @include breakpoint('s') {
            font-size: $font-size-very-small;
            height: 2.5rem;
        }
    }

</style>