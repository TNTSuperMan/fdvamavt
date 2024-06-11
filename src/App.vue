<script setup>
import {ref,computed} from "vue"

import Home from "./Home.vue"
import Setting from "./Setting.vue"
import Prep from "./Prep.vue"
import Game from "./Game.vue"
const routes = [
  Home,Setting,Prep,Game
]
const path = ref(0)
window.addEventListener("hashchange",e=>path.value=window.location.hash)
const page = computed(e=>routes[path.value] || Home)
const acm = ref(0)
const level = ref(1)

function cfg(fcm){
  console.log(fcm)
  acm.value = fcm / 5;
  path.value++;
}
</script>
<template>
    <component :is="page" @next="path++" @cfg="cfg" :acm="acm" :level="level"/>
</template>