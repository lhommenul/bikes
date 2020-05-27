<template>
    <div>
        <!-- Config Account -->
        <div id="step_1_config">
            <label for="">
                <h2>Selectionner le type de compte</h2>
                <div>
                    <button :class="{not_selected_button: account_type != 0, selected_button: account_type == 0}" @click="account_type = 0">Candidat</button>
                    <button :class="{not_selected_button: account_type != 1, selected_button: account_type == 1}" @click="account_type = 1">Moniteur</button>
                    <button :class="{not_selected_button: account_type != 2, selected_button: account_type == 2}" @click="account_type = 2">Auto Ecole</button>
                </div>
            </label>
            <label for="" v-if="account_type == 0">
                Candidat
            </label>
            <label for="" v-if="account_type == 1">
                Moniteur
            </label>
            <label for="" v-if="account_type == 2">
                Auto Ecole
            </label>                        
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            account_type:Number
        }
    }
}
</script>

<style scoped>
button{
    font-size: 20px;
    background-color: whitesmoke;
    border-style: none;
    margin: 10px;
    padding: 8px;
    border-radius: 3px;
    cursor: pointer;
}
.not_selected_button{
    background-color: red;
    color: white;
}
.selected_button{
    background-color: rgb(18, 153, 119);
    color: white;
}
</style>