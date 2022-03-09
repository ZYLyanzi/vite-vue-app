<script setup>
import { ref, reactive, computed, watch} from 'vue'
import HelloWorld from './components/HelloWorld.vue'
let msg = ref("这是个demo");
const user = reactive({
  name: 'yanzi',
  age: 18
})
function reverMsg(val){
  return val+"ssss"
}
function changeName(event){
  user.name = '钟燕龄'
  console.log("event", event)
}
const  resMsg = computed(() => {
  return msg.value+'11111';

})
function setMsg(value){
  msg.value = value+'yanzi'
}
watch(msg, (newValue, oldValue) => {
  console.log("newValue", newValue)
  console.log("oldValue", oldValue)
})

var F = function() {};

Object.prototype.a = function() {
  console.log('a');
};

var f = new F();
f.a;


</script>

<template>
  <h1>用户{{user.name}}</h1>
  <h1>年龄{{user.age}}</h1>
  <button @click="changeName">修改名字</button>
  <h1>{{msg}}</h1>
  <h1>{{reverMsg(msg)}}</h1>
  <h1>{{resMsg}}</h1>
  <h1>{{resMsg}}</h1>
  <button @click="setMsg(msg)">点击变化</button>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3 + Vite" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
