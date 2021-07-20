<template>
    <div class="container-footer">
        <p>created by <b><a href="https://robin-minster.fr">Minster Robin</a></b> - devChallenges.io</p>
    </div>
</template>

<script>
    export default {
        name: "Footer"
    }
</script>

<style lang="scss" scoped>
    @import "../styles/variables";
    .container-footer {
        text-align: center;
        margin: 100px 0 0;
        font-family: $font-family-primary;
        font-size: $font-size-small;
        font-weight: 500;
        color: $color-gray-5;
    }
</style>