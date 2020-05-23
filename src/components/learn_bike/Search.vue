<template>
    <div @mouseleave="input_clicked = false">
        <div>
            <div>
                <input type="text" placeholder="Trouvez votre Moto Ecole" @click="input_clicked = true">
                <i><img src="" alt="localisation"></i>
                <button>Rechercher</button>
            </div>
            <div id="results_show" :class="{close_panel_result:input_clicked == false,open_panel_result:input_clicked == true}">
                <Result/>
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
.open_panel_result{
    display: block;
height: 300px;
width: 300px;
background-color: red;
}
.close_panel_result{
    display: none;
height: 0px;
width: 0px;
}
</style>