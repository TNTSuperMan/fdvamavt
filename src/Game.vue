<script setup>
import "./asset/graphdom.min.js"
import {ref} from "vue"
const props = defineProps(["level","acm"])
const text = ref()
const level = props.level
const $ = GraphDom

const speed = 700 / level
const keta = Math.floor((level / 30) ** 10)
const range = props.acm * level
const size = props.acm / level * 2
function tp(){
    $("p").x = window.innerWidth / 2
    $("p").x += Math.random() * (range * 2) - range
    $("p").y = window.innerHeight / 2
    $("p").y += Math.random() * (range * 2) - range
    $("p").style.fontSize = size + "px"
}
setInterval(tp,speed)
console.log(speed)
</script>
<template>
    <input type="number" v-model="level">
    <button @click="tp">upd</button>
    <p ref="text">4545</p>
</template>