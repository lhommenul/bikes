<template>
    <div class="container_professor">
        <img class="picture_professor" src="https://www.pavilionweb.com/wp-content/uploads/2017/03/man-300x300.png" alt="professor picture">
        <h1>{{data.name+' '+data.sub_name}}</h1>
    </div>
</template>

<script>
export default {
    props:{
        data:Object
    }
    
}
</script>

<style scoped>
.container_professor{
    background-color: rgb(255, 255, 255);
    box-shadow: 2px 2px 6px grey;
    margin: 5px;
    border-radius: 5px;
    width: 250px;
    height: 350px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.picture_professor{
    height: 30%;
}
</style>