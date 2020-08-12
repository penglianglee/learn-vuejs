<template>
<div>
    <CheckList v-for="name in names" :key="name.id" :name="name.name" :checkednames="checkednames"></CheckList>
    <span>Checked names: {{ checkednames}}</span>
</div>
</template>

<script>
import CheckList from "./components/CheckList"

export default {
    components: {
        CheckList,
    },
    data: function(){
        return {
            checkedNames:[], 
            names:[
                {
                    id:1,
                    name:"Vue",
                },
                {
                    id:2,
                    name:"React",
                },
                {
                    id:3,
                    name:"Angular"
                }
            ]           
        }
    },
    computed: {
        checkednames: {
            get: function(){
                console.log("get:"+this.checkedNames);
                return this.checkedNames
            },
            set: function(newVal) {
                console.log("set:"+newVal);
                this.checkedNames = newVal
            }
        }
    }   
}
</script>

