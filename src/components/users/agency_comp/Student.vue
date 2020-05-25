<template>
    <div class="container_student">
        <img class="picture_student" src="https://www.pavilionweb.com/wp-content/uploads/2017/03/man-300x300.png" alt="student picture">
        <h1>{{data.name+' '+data.sub_name}}</h1>
        <h2>00h00</h2>
        <h3>Montant Payé = 300€</h3>
        <button>permis category : moto</button>
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
.container_student{
    background-color: whitesmoke;
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
.picture_student{
    height: 30%;
}
</style>