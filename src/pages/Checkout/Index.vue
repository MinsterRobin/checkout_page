<template>
    <div class="page-layout">
        <PageTitle title="Checkout"/>
    </div>
</template>

<script>
    import PageTitle from "@/components/PageTitle";
    export default {
        name: "Index",
        components: {PageTitle}
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
</style>