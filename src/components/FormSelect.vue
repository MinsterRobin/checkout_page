<template>
    <div class="form-select-layout">
        <FormLabel v-bind:label="label" v-bind:id="id">{{label}}</FormLabel>
        <div class="select-container">
            <img v-bind:src="require('@/assets/' + icon + '.svg')" alt="Input icon"/>
            <select v-bind:class="{selected: isSelected}"
                    v-bind:name="id"
                    v-bind:id="id"
                    required
                    v-on:change="isSelected = true"
            >
                <option class="placeholder" value="" disabled selected>{{placeholder}}</option>
                <option v-for="option in options" :key="option.index">{{option}}</option>
            </select>
        </div>
    </div>
</template>

<script>
    import FormLabel from "@/components/FormLabel";
    export default {
        name: "FormSelect",
        components: {FormLabel},
        props: {
            label: String,
            placeholder: String,
            id: {
                type: String,
                required: true
            },
            icon: {
                type: String,
                required: true
            },
            options: {
                type: Array,
                required: true
            }
        },
        data() {
            return {
                isSelected: false
            };
        }
    }
</script>

<style lang="scss" scoped>
    @import "../styles/breakpoints";
    @import "../styles/variables";

    .form-select-layout {
        flex: 1;
        display: flex;
        flex-direction: column;
        row-gap: 6px;

        font-family: $font-family-primary;
        font-size: $font-size-very-small;
        font-weight: 600;
        width: 100%;
        min-width: 190px;
    }

    .select-container {
        position: relative;
        display: flex;
        align-items: center;
    }

    img {
        position: absolute;

        margin-left: 1rem;
    }

    select {
        font-family: $font-family-primary;
        font-weight: 600;
        font-size: $font-size-regular;
        line-height: 20px;
        padding-left: 3rem;
        color: $color-gray-3;

        width: 100%;
        height: 56px;
        border: 1px solid $color-gray-3;
        border-radius: 12px;

        /*-- Custom arrow --*/
        -webkit-appearance: none;
        appearance: none;
        background-image: url(../assets/arrow.png);
        background-repeat: no-repeat;
        background-position-y: 50%;
        background-position-x: 95%;

        @include breakpoint('s') {
            font-size: $font-size-very-small;
            height: 2.5rem;
        }
    }

    .placeholder {
        color: $color-gray-3;
    }

    option {
        @include breakpoint('s') {
            font-size: $font-size-very-small;
            height: 2.5rem;
        }
    }

    .selected {
        color: $color-gray-1;
    }

</style>