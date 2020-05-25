<template>
    <div>
        <div>
            <!-- background image -->
            <div class="agence_banner_container" :style="{'background-image':'url('+agence.background_image+')'}">
                <h1 class="agence_title_name">{{agence.name}}</h1>
                <!-- contactez l'agence -->
                <div class="container_contact_info">
                    <button>Prendre Contact</button>
                </div>
            </div>
            <div>
                <div class="list_container_option_lessons">
                    <div class="container_add">
                        <h2>Voir les forfaits de conduite</h2>
                    </div>
                    <div class="container_add">
                        <h2>Voir les tarifs de formation</h2>
                    </div>
                    <div class="container_add">
                        <h2>Nos Eleves et Offres</h2>
                    </div>                    
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            agence:{
                name:'Default',
                background_image:'https://www.twintour.net/images/freeride.jpg'
            }
        }
    }
}
</script>

<style scoped>
.agence_banner_container{
    background-position: center;
    background-size: cover;
    height: 400px;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
}
.agence_title_name{
    grid-column: 2;
}
.container_add{
    margin: 10px;
    height: 100%;
    width: 100%;
    background-color: grey;
}
.container_contact_info{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    grid-row: 2;
    grid-column: 3;
}
.list_container_option_lessons{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr;
    gap: 10px;
    height: 240px;
}
</style>