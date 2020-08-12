<template>
<div>
    <input type="checkbox" :id="name" :value="name" v-model="checkednames" />
    <label :for="name">{{name}}</label>
</div>
</template>

<script>
export default {
    props: {
        name:String,
        checkednames:[],
    }
}
</script>