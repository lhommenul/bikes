<template>
  <div :class="{bikes_stores_large : posi==true, bikes_stores_small : posi == false}" :style="{'background-image':'url(https://static4.pagesjaunes.fr/media/cviv/06400781-c595e66ada1b9022f7ab30cb008cdd30)'}">
    <div>
      <h1>Nom Moto Ecole</h1>
      <h4>rating stars</h4>
    </div>
    <div>
      <ul>
        <li><button class="lesson_given">Moto</button></li>
        <li><button class="lesson_given">Voiture</button></li>
        <li><button class="lesson_given">Poids Lourd</button></li>
      </ul>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
    props:{
        posi:Boolean,
        agency:{
          name:String,
          rating:Number,
          
        }
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
.lesson_given{
  cursor: pointer;
  margin: 5px;
  padding: 5px;
  border-radius: 3px;
  font-size: 16px;
  background-color: rgb(43, 87, 117);
  color: white;
  border-style: none;
}
</style>