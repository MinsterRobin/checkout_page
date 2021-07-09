<template>
    <div class="form-input-layout">
        <label v-bind:for="id">{{label}}</label>
        <input
                v-bind:type="type"
                v-bind:pattern="pattern"
                v-bind:name="id"
                v-bind:id="id"
                v-bind:placeholder="placeholder"
                required
        >
    </div>
</template>

<script>
    export default {
        name: "FormInput",
        props: ['label', 'type', 'id', 'placeholder', 'pattern']
    }
</script>

<style lang="scss" scoped>
    @import "../styles/breakpoints";
    @import "../styles/variables";

    .form-input-layout {
        display: flex;
        flex-direction: column;

        font-family: $font-family-primary;
        font-size: $font-size-very-small;
        font-weight: 600;
    }

    label {
        font-family: $font-family-primary;
        font-size: $font-size-very-small;
        color:$color-gray-2;
    }

    input {
        font-family: $font-family-primary;
        font-weight: 600;
        font-size: $font-size-regular;
        line-height: 20px;

        height: 56px;
        border: 1px solid #828282;
        border-radius: 12px;
    }

</style>