<template>
    <router-link :to="message_link" class="list_style">
        <div>
            {{message_title}}
        </div>
        <div>
            {{message_sub_title}}
        </div>
    </router-link>
</template>

<script>
export default {
    props:{
        message_title:String,
        message_sub_title:String,
        message_link:String,
    },
    data(){
        return{

        }
    }
}
</script>

<style scoped>
.list_style{
    border-radius: 5px;
    height: 100%;
    width: 100%;
    background-color: black;
    color: white;
}
</style>

