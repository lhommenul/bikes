<template>
  <div :class="{bikes_stores_large : posi==true, bikes_stores_small : posi == false}" :style="{'background-image':'url(https://static4.pagesjaunes.fr/media/cviv/06400781-c595e66ada1b9022f7ab30cb008cdd30)'}">
    <h1>Nom Moto Ecole</h1>
    <h4>rating stars</h4>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
    props:{
        posi:Boolean
    },
    components: {

    }
}
</script>

<style scoped>
.bikes_stores_large{
background-color: black;
height: 400px;
width: 90%;
margin: 3px;
background-position: center;
background-size: cover;
}
.bikes_stores_small{
    height: 300px;
    width: 400px;
    background-color: red;
    margin: 3px;
    background-position: center;
    background-size: cover;
}

</style>