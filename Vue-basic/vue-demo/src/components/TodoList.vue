<template>
    <ul @click="aler">
        <slot></slot>
    </ul>
</template>

<script>
export default {
    data: function () {
        return {};
    },
    methods: {
        aler() {
            alert("ohh~");
        },
    },
};
</script>

<style scoped>
ul {
    list-style-type: none;
    padding-inline-start: 0;
}
</style>