<template>
    <div @mouseleave="input_clicked = false">
        <div id="container_search_input_result_box">
            <div id="search_container_elements">
                <input id="input_field" type="text" placeholder="Trouvez votre Moto Ecole" @click="input_clicked = true">
                <i><img src="" alt="localisation"></i>
                <button id="search_button">Rechercher</button>
            </div>
            <div id="results_show" :class="{close_panel_result:input_clicked == false,open_panel_result:input_clicked == true}">
                <Result :message_title="'Touvez Près de Chez Vous'" :message_link="'/user'" :message_sub_title="'37500,  3 Auto Ecoles Trouvées'"/>
                <Result :message_title="'Moto Ecole La Moins Chère'" :message_link="'/user'" :message_sub_title="'Le premier tarif est de 300€'"/>
                <Result :message_title="'Moto Ecole La Mieux Notée'" :message_link="'/user'" :message_sub_title="'4.9/5'"/>
                <Result :message_title="'Moto Ecole La PLus Pédagogue'" :message_link="'/user'" :message_sub_title="'Chinon, Moto Ecole du Vieux Port'"/>
            </div>
        </div>
    </div>
</template>

<script>
import Result from './Result'
export default {
    data(){
        return{
            input_clicked : false
        }
    },
    methods:{
        displayResults(){
            // var box_result = document.getElementById('results_show');            
        }
    },
    components:{
        Result
    }
}
</script>

<style scoped>
#results_show{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    gap: 15px;
}
.open_panel_result{
    transition: 0.3s;
    display: block;
    visibility: visible;
    height: 300px;
    width: 100%;
}
#search_container_elements{
    margin-bottom: 20px;
}
.close_panel_result{
    transition: 0.1s;
    display: none;
    visibility: hidden;
    height: 0px;
    width: 100%;
}
#search_button{
    font-size: 20px;
    padding: 10px;
    border-style: none;
    border-radius: 3px;
    color: orangered;
    cursor: pointer;
}
#input_field{
    height: 40px;
    width: 50%;
    border-radius: 15px;
    border-style: none;
    background-color: whitesmoke;
    text-indent: 10px;
    font-size: 20px;
}
</style>