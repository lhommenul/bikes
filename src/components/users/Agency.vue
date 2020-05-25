<template>
    <div>
        <!-- Planing -->
        <div>
            <Planing/>
        </div>
        <!-- ================= -->
        <div>
            <div>
                <!-- Eleves -->
                <div :class="{container_students: menus.students.open == false,open_container_students: menus.students.open == true}">
                    <div v-for="student in students" :key="student.id">
                        <Student :data="student"/>
                    </div>
                </div>                
                <div>
                    <button @click="menus.students.open = !menus.students.open" class="see_more">Voir tous les élèves</button>
                </div>
            </div>
            <!-- Professor -->
            <div>
                <div :class="{container_professor: menus.professors.open == false,open_container_professor: menus.professors.open == true}">
                    <div v-for="professor in professors" :key="professor.id">
                        <Professor :data="professor"/>  
                    </div>                    
                </div>
                <div>
                    <button @click="menus.professors.open = !menus.professors.open" class="see_more">Voir tous les professeurs</button>
                </div>
            </div>        
        </div>
    </div>
</template>

<script>
import Student from './agency_comp/Student'
import Planing from './agency_comp/Planing'
import Professor from './agency_comp/Professor'
export default {
    data(){
        return{
            students:[
                {
                    name:'Tom',
                    sub_name:'Albert'
                },                {
                    name:'Anna',
                    sub_name:'Gigo'
                },                {
                    name:'Albert',
                    sub_name:'To'
                },                {
                    name:'Maxime',
                    sub_name:'DeLaRue'
                },                {
                    name:'Arthur',
                    sub_name:'Next'
                },
            ],
            professors:[
                {
                    name:'Jack',
                    sub_name:'Morelo'
                },                {
                    name:'Jimi',
                    sub_name:'Hendrix'
                },                
            ],
            planing:{},
            menus:{
                students:{
                    open:false
                },
                professors:{
                    open:false
                },                
            }
        }
    },
    components:{
        Student,
        Planing,
        Professor
    }
}
</script>

<style scoped>
.container_students,.container_professor{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    height: 300px;
    overflow: hidden;
}
.open_container_students,.open_container_professor{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    height: auto;
    overflow: hidden;
}
.see_more{
    cursor: pointer;
    width: 80%;
    background-color: rgb(14, 175, 156);
    color: white;
    border-radius: 15px;
    border-style: none;
    padding: 5px;
    font-size: 18px;
    margin: 15px;
}
</style>
    