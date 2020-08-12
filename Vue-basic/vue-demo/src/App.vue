<template>
    <!--<div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
    -->
    <div id="app">
        {{ msg }}
        <input type="text" :value="msg" @input="handleChange" />
        <button v-on:click="changeState">逆转</button>
        <br />

        <CheckBox></CheckBox>
<!--         
        <input type="checkbox" id="react" value="React" v-model="checkedNames" />
        <label for="react">React</label>
        <input type="checkbox" id="vue" value="Vue" v-model="checkedNames" />
        <label for="vue">Vue</label>
        <input type="checkbox" id="angular" value="Angular" v-model="checkedNames" />
        <label for="angular">Angular</label>
        <span>Checked names: {{ checkedNames}}</span>
         -->

        <todo-list>
            <todo-item
                @logClick="handleLog"
                v-for="item in items"
                v-bind:key="item.id"
                :title="item.title"
                :del="item.del"
            >
                <template v-slot:pre="{state}">
                    <span>{{state}}</span>
                </template>
            </todo-item>
        </todo-list>
    </div>
</template>

<script>
import TodoList from "./components/TodoList"
import TodoItem from "./components/TodoItem"
import CheckBox from "./components/CheckBox"
import CheckList from "./components/CheckList"

export default {
    name: "App",
    components: {
        TodoItem,
        TodoList,
        CheckBox,
    },
    data: function () {
        return {
            checkedNames: [],
            msg: "hello world!",
            items: [
                {
                    id: 1,
                    title: "React学习",
                    del: true,
                },
                {
                    id: 2,
                    title: "Vue学习",
                    del: false,
                },
            ],
            
        };
    },
    methods: {
        changeState: function () {
            this.msg = this.msg.split("").reverse().join("");
        },
        handleLog(val) {
            console.log(val);
        },
        handleChange(e) {
            this.msg = e.target.value;
        },
    },
};
</script>
