<template>
    <li>
        <slot v-if="!del" name="pre" :state="mood.good"></slot>
        <slot v-else name="pre" :state="mood.bad"></slot>
        <span v-if="!del">{{title}}</span>
        <span v-else style="text-decoration: line-through;">{{title}}</span>
        <button @click.stop="handleClick">kiki</button>
    </li>
</template>

<script>
export default {
    props: {
        title: String,
        del: {
            type: Boolean,
            default: false,
        },
    },
    data: function () {
        return {
            mood: {
                good: "happy ",
                bad: "sad ",
            },
        };
    },
    methods: {
        handleClick() {
            console.log("todo-item子组件事件传递");
            this.$emit("logClick", this.title);
        },
    },
};
</script>