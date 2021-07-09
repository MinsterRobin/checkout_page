<template>
    <label v-bind:for="id">{{label}}</label>
</template>

<script>
    export default {
        name: "FormLabel",
        props: {
            label: {
                type: String,
                required: true
            },
            id: {
                type: String,
                required: true
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import "../styles/breakpoints";
    @import "../styles/variables";

    label {
        font-family: $font-family-primary;
        font-size: $font-size-very-small;
        color:$color-gray-2;

        @include breakpoint('s') {
            font-size: $font-size-tiny;
        }
    }
</style>