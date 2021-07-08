<template>
    <p>{{title}}</p>
</template>

<script>
    export default {
        name: "PageTitle",
        props: ['title']
    }
</script>

<style lang="scss" scoped>
    @import "../styles/breakpoints";
    @import "../styles/variables";

    p {
        font-family: $font-family-primary;
        font-size: $font-size-very-large;
        font-weight: 600;
        color: $color-gray-4;

        @include breakpoint('s') {
            font-size: $font-size-large;
        }
    }
</style>