<template>
    <div class="planing_element_container_main">
        <div>
            <button class="button_add_option" @click="add_student = true">Ajouter un Eleve</button>
            <button class="button_add_option" @click="add_teacher = true">Ajouter un Professeur</button>
        </div>
        <!-- Dialog -->
        <!-- Ajouter un Eleve -->
        <AddStudent  @closeStudentWindow="add_student = false" :add_student="add_student" />
        <AddMonitor @closeTeacherWindow="add_teacher = false" :add_teacher="add_teacher"/>
        <v-calendar
            :events="events"
            :now="today"
            :value="today"    
            @click:date="daily_calendar = true, daily_calendar_payload = $event"
        ></v-calendar>
        <v-calendar-daily
            v-if="daily_calendar"
            :events="events"
            :now="daily_calendar_payload.date"
        >
         <template v-slot:interval="{ hour }">
            <div
              class="text-center"
            >
              <h1>{{displayEventDay(hour)}}</h1>
            </div>
          </template>
        </v-calendar-daily>
        <div class="close_fen" v-if="daily_calendar" @click="daily_calendar = false">Fermer La Fenetre</div>
        <v-btn height="60px" v-if="daily_calendar" id="floating_add_button_event">+</v-btn>
    </div>
</template>

<script>
import AddStudent from './AddStudent'
import AddMonitor from './AddMonitor'
export default {
    data(){
        return{
            today: '2020-05-28 09:00',
            events: [
                {
                name: 'Weekly Meeting',
                start: '2020-05-27 09:00',
                end: '2020-05-27 10:00',
                },
                {
                name: 'Thomas\' Birthday',
                start: '2019-01-10',
                },
                {
                name: 'Mash Potatoes',
                start: '2019-01-09 12:30',
                end: '2019-01-09 15:30',
                },
            ],
            day_events: [
                {
                name: 'Weekly Meeting',
                start: '2020-05-27 09:00',
                end: '2020-05-27 10:00',
                },
                {
                name: 'Thomas\' Birthday',
                start: '2019-01-10',
                },
                {
                name: 'Mash Potatoes',
                start: '2019-01-09 12:30',
                end: '2019-01-09 15:30',
                },
            ],
            daily_calendar:false,
            daily_calendar_payload:null,
            add_student:false,      
            add_teacher:false,
        }
    },
    methods:{
        displayEventDay(){           
            return this.daily_calendar_payload.date
        },
        addEventInTheDay(){
            console.log('addEventInTheDay')
        },
    },
    components:{
        AddStudent,
        AddMonitor
    }
}
</script>

<style scoped>
textarea{
    border-style: none;
    background-color: whitesmoke;
    color: black;
    border-radius: 15px;
}
.close_fen{
    width: 100%;
    background-color: red;
    color: white;
    font-size: 25px;
    padding: 5px;
    margin: 10px;
    cursor: pointer;
}
#floating_add_button_event{
    position: fixed;
    bottom: 20px;
    right: 20px;
    border-radius: 50%;
    font-size: 24px;
    background-color: pink;
    color: white;
}
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