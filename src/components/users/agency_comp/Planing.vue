<template>
    <div class="planing_element_container_main">
        <div>
            <button class="button_add_option">Ajouter un Eleve</button>
            <button class="button_add_option">Ajouter un Professeur</button>
        </div>
        <div class="container_tiles_date">
            <div iv class="tile_date" v-for="day in nb_days" :key="day.id">
                {{day}}
                <button class="add_event" @click="add_event.displayed = true">Ajouter</button>
            </div>    
        </div>    
        <div :class="{closed_menu : add_event.displayed == false, opened_menu : add_event.displayed == true}">
            <button class="close_add_event_btn" @click="add_event.displayed = false">x</button>
            <div class="container_information">
                <h1>Date</h1>
                <div id="step_1">
                    <label for="">
                        <h3>Type d'évènement : </h3>
                        <button class="style_button_open_close_list">Events</button>
                    </label>
                    <div>
                        <ul>
                            <li class="option_selection" @click="createEvent('lmoto')">Leçon de Moto</li>
                            <li class="option_selection" @click="createEvent('lvoiture')">Leçon de Voiture</li>
                            <li class="option_selection" @click="createEvent('lscooter')">Leçon de Scooter</li>
                            <li class="option_selection" @click="createEvent('lpoidslourds')">Leçon de Poids Lourds</li>
                            <li class="option_selection" @click="createEvent('autre')">Autre</li>
                        </ul>
                    </div>
                </div>
                <div id="step_2">

                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            data:{
                nb_days:0,
            },
            add_event:{
                displayed:true
            },
            starting_data_point:''
        }
    },
    beforeCreate(){
        var actual = new Date()
        const month = actual.getMonth();
        var here = new Date(actual.getFullYear(),month,0)
        const number_of_days = here.getDate()
        this.nb_days = number_of_days            
    },
    methods:{
        createEvent(event_name){
            switch (event_name) {
                case 'lmoto':

                break;
                case 'lvoiture':

                break;
                case 'lscooter':

                break;
                case 'lpoidslourds':

                break;
                case 'autre':

                break;
                default:

                break;
            }
        }
    },
}
</script>

<style scoped>
.container_tiles_date{
    height: 300px;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
.tile_date{
    min-height: 80px;
    height: auto;
    width: 60px;
    box-shadow: 2px 2px 6px rgba(20, 20, 20, 0.603);
    border-radius: 3px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.close_add_event_btn{
    font-size: 20px;
    background-color: red;
    color: white;
    border-radius: 50%;
    border-style: none;
    padding: 10px;
    height: 30px;
    width: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.option_selection{
    background-color: rgb(11, 74, 133);
    color: white;
    border-radius: 15px;
    font-size: 16px;
    margin: 3px;
    cursor: pointer;
    padding: 10px;
}
.option_selection:hover{
    background-color: rgb(13, 106, 192);
}
.style_button_open_close_list{
    padding: 10px;
    border-style: none;
    border-radius: 15px;
    font-size: 18px;
}
#input_add_event_list{
    border-radius: 15px;
    border-style: none;
    background-color: whitesmoke;
    text-indent: 5px;
    padding: 5px;
    font-size: 20px;
}
.container_add_event_information{
    background-color: white;
}
.add_event{
    background-color: brown;
    border-style: none;
    border-radius: 3px;
    padding: 5px;
    color: white;
    cursor: pointer;
}
.closed_menu{
    visibility: hidden;
}
.opened_menu{
    visibility: visible;
    position: fixed;
    top: 0px;
    left: 0px;
    right: 0px;
    bottom: 0px;
    background-color: rgba(255, 255, 255, 0.5);
    height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}
.container_information{
    display: flex;
    justify-self: center;
    align-self: center;
    background-color: white;
    box-shadow: 2px 2px 6px rgba(128, 128, 128, 0.281);
    width: 80%;
    height: 400px;
}
.button_add_option{
    background-color: rgb(255, 173, 66);
    color: white;
    border-style: none;
    padding: 5px;
    font-size: 20px;
    border-radius: 3px;
    margin: 3px;
}
</style>