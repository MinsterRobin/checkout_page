<template>
    <div>
        <Index/>
    </div>
</template>

<script>


import Index from "@/pages/Checkout/Index";
export default {
    name: 'App',
    components: {Index},
}
</script>

<style lang="scss">
    @import "styles/global";

    .container {
        display: grid;
        width: 500px;
        grid-template-columns: 50px 1fr 2fr;
    }

    .container:hover {
        transform: scale(0.5);
    }
</style>
