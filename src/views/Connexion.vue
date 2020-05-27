<template>
    <div>
        <h1>Connexion</h1>
        <div>
            <form action="" class="connection_form" method="post">
                <input type="text" placeholder="identifiant">
                <input type="password" placeholder="mot de passe">
                <button>Connexion</button>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
.connection_form{
    display: flex;
    flex-direction: column;
}
button{
    border-style: none;
    background-color: rgb(0, 140, 255);
    color: white;
    font-size: 20px;
    padding: 5px;
    cursor: pointer;
}
input{
    font-size: 20px;
    padding: 5px;
    border-radius: 5px;
    border-style: none;
    background-color: whitesmoke;
    margin: 5px;
    text-indent: 3px;
}
</style>