<script setup>
import {ref,computed} from "vue"
const fcmpx = ref(200)
const style = computed(e=>
    "width:" + fcmpx.value + "px"
)
</script>
<template>
    <p>1:下の白い箱の横幅が5cmになるように下の数値を調整してください</p>
    <input type="number" min="1" v-model="fcmpx"><br>
    <div class="testbox" :style="style"></div>
    <button @click="$emit('cfg',fcmpx)">設定完了</button>
</template>
<style scoped>
input{
    background:#000;
    padding:3px;
    color:#fff;
    padding:5px;
    border-radius:5px;
    font-size:20px;
    width:100px;
}
.testbox{
    height:100px;
    background:#fff;
    margin:auto;
}
</style>