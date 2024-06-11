<script setup>
const props = defineProps(["level"])
</script>
<template>
    <h2>レベル{{props.level}}の準備が出来たら下のボタンを押してください↓</h2>
    <button @click="$emit('next')">準備完了</button>
</template>