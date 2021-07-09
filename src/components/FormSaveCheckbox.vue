<template>
    <div class="save-layout">
        <input type="checkbox" name="save" id="save">
        <FormLabel id="save" label="Save this information for next time" />
    </div>
</template>

<script>
    import FormLabel from "@/components/FormLabel";
    export default {
        name: "FormSaveCheckbox",
        components: {FormLabel}
    }
</script>

<style lang="scss" scoped>
    @import "../styles/breakpoints";
    @import "../styles/variables";

    .save-layout {
        display: flex;
        align-items: center;
        column-gap: 0.5rem;
    }
</style>