<template>
    <div>
        <div id="user_informations">
            <div>
                <h1>User Name</h1>
                <h2>Formation En Cours</h2>
                <h2>adresse email</h2>
                <img src="" alt="Photo de profil">
            </div>
        </div>
        <button id="button_modify_info" @click="modify_info = !modify_info">Modifier Informations</button>
        <div id="user_add_informations" :class="{open_modify_info:modify_info == true,close_modify_info:modify_info == false}">
            <div>
                <div>
                    <input type="text" placeholder="modifier votre adresse email">
                </div>
                <div>

                </div>
            </div>
        </div>
    </div>    
</template>

<script>
export default {
    data(){
        return{
            modify_info:false
        }
    }
}
</script>

<style>
.open_modify_info{

}
.close_modify_info{
display: none;    
}
#button_modify_info{
    position: absolute;
    bottom: 20px;
    right: 20px;
    height: 100px;
    width: 100px;
    border-radius: 50%;
    border-style: none;
    text-align: center;
    background-color: rgb(27, 27, 27);
    color: white;
}
</style>