<template>
    <div>
        <span><img src="https://vuejs.org/images/logo.svg" /> <h3>{{title}}</h3></span>
        <Button @toggle="$emit('toggle')" />
    </div>
</template>
<script>
import Button from "./Button.vue"
export default {
    name:"Header",
    props:{
        title:String,
    },
    components:{
        Button
    },
    emits:['toggle']
}
</script>

<style scoped>
div{
    height:50px;
    background-color: rgba(137, 43, 226, 0.322);
    border-radius: 4px;
    padding: 10px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
}
span{
    display: flex;
    flex-direction: row;
    height: 20px;
    margin-left: 10px;

}
span>h3{
    align-self:center;
}
img{
    margin-right: 10px;
}
</style>