<template>
    <div class="espace_container_connection">
        <router-link to="/connexion" class="connection_button_space">Connexion</router-link>
        <router-link class="connection_button_space_create" to="/create_account">Creer un Compte</router-link>
    </div>
</template>

<script>
export default {
    data(){
        return{

        }
    }
}
</script>

<style scoped>
.espace_container_connection{
    margin: 10px;
}
.connection_button_space,.connection_button_space_create{
font-size: 18px;
padding: 10px;
margin: 5px;
background-color: rgb(0, 148, 116);
color: white;
border-style: none;
border-radius: 5px;
}
.connection_button_space_create{
background-color: rgb(7, 78, 126);
}
</style>