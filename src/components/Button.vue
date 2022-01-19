<template>
    <button @click="$emit('toggle')">Add</button>
</template>

<script>
export default {
    name:"Button",
    emits:['toggle']

}
</script>

<style scoped>
button{
    padding:12px;
    background: rgb(190, 252, 128);
    border-radius: 5px;
    border:0px;
}
</style>