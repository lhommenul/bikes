<template>
    <div class="planing_element_container_main">
        <div>
            <button class="button_add_option">Ajouter un Eleve</button>
            <button class="button_add_option">Ajouter un Professeur</button>
        </div>
        <div class="container_tiles_date">
            <div v-show="tile.selected == false" @click="tile.selected = true, tile.date.year = year, tile.date.month = monthConverter(), tile.date.day = day" :class="{tile_date_after: day > today, tile_date_today: day == today, tile_date_past: day < today}" v-for="day in total_nb_days" :key="day.id">
                {{day}}
                {{monthConverter()}}
                {{year}}
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
        <!-- Day -->
        <div v-show="tile.selected">
            <button @click="tile.selected = false">Retour</button>         
            {{tile.date.day}}
            {{tile.date.month}}
            {{tile.date.year}}
            <div class="container_elements_tiles_day">
                <div>
                    <div class="hour_tile_day" v-for="item in 24" :key="item.id">
                        {{ 0+item+'H00' }}
                    </div>     
                </div>
                <div class="column">
                    <div @click="add_event.displayed = true" class="hour_tile_day" v-for="item in 24" :key="item.id">
                        {{ item }}
                    </div>                     
                </div>                 
                <div class="column">
                    <div @click="add_event.displayed = true" class="hour_tile_day" v-for="item in 24" :key="item.id">
                        {{ item }}
                    </div>                     
                </div>       
                <!-- Event Creator -->
                <div id="event_creator_container">
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
                total_nb_days:Number,
                today:Number,
                month:String,
                year:String
            },
            tile:{
                selected:false,
                date:{
                    day:String,
                    month:String,
                    year:Number
                }
            },
            add_event:{
                displayed:false
            },
            starting_data_point:''
        }
    },
    beforeCreate(){
        var actual = new Date()
        const month = actual.getMonth();
        var here = new Date(actual.getFullYear(),month,0)
        this.total_nb_days = here.getDate()+1;
        this.today = actual.getDate()
        this.month = actual.getMonth()
        this.year = actual.getFullYear()
        console.log(this.today);        
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
        },
        monthConverter(){
            switch (this.month) {
                case 0:                    
                    return 'janvier'
                case 1:                    
                    return 'fevrier'
                case 2:                    
                    return 'mars'
                case 3:                    
                    return 'avril'                                                    
                case 4:
                    return 'mai'                    
                case 5:                    
                    return 'juin'
                case 6:                    
                    return 'juillet'                    
                case 7:                    
                    return 'août'
                case 8:                    
                    return 'septembre'
                case 9:                    
                    return 'octobre'
                case 10:                    
                    return 'novembre'                                                    
                case 11:                    
                    return 'décembre'
                default:
                    console.error('Error while founding month');                    
                    break;
            }
            return 
        },
    },
}
</script>

<style scoped>
.row{
    display: flex;
    flex-direction: row;
}
#test_split{
    height: 600px;
    background-color: whitesmoke;
    width: 200px;
}
#event_creator_container{
    display: flex;
}
.column{
    display: flex;
    flex-direction: column;
}
.container_tiles_date{
    height: 300px;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
.container_elements_tiles_day{
    display: flex;
    flex-direction: row;
}
.hour_tile_day{
    width: 200px;
    background-color: whitesmoke;
    padding: 5px;
    height: 25px;
    font-size: 18px;
    border: solid 0.5px grey;
}
.tile_date_after, .tile_date_today, .tile_date_past{
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
.scale_up{
    height: 400px;
}
.tile_date_past{
    background-color: grey;
}
.tile_date_today{
    background-color: red;
    color: white;
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
    position: fixed;
    top: 0px;
    left: 0px;
    right: 0px;
    bottom: 0px;
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