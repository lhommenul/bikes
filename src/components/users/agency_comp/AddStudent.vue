<template>
    <v-dialog overlay-color="white" persistent=true v-model="add_student">
        <!-- Close The Dialog -->
        <v-btn @click="$emit('closeStudentWindow')" color="red"><h3>Fermer</h3></v-btn>
        <v-card>
            <!-- Card Title -->
            <v-card-title primary-title>
                <h2>Ajouter un élève</h2>
            </v-card-title>
            <!-- Content / Form -->
            <v-card-text>
                <v-form>
                    <v-text-field
                        :counter="100"
                        label="Prénom"
                        required
                    ></v-text-field>
                    <v-text-field
                        :counter="100"
                        label="Nom"
                        required
                    ></v-text-field>
                    <v-text-field
                        :counter="100"
                        label="Adresse Email"
                        required
                    ></v-text-field>                        
                    <v-overflow-btn
                        class="my-2"
                        :items="dropdown_edit"
                        label="Sexe"
                        item-value="text"
                    ></v-overflow-btn>             
                    <v-btn type="submit" color="success">Ajouter</v-btn>          
                </v-form>
            </v-card-text>
        </v-card>
    </v-dialog>
</template>

<script>
export default {
    props:{
        add_student : Boolean
    },
    data(){
        return{
            dropdown_edit: [
                { text: 'homme' },
                { text: 'femme' },
            ],                  
        }
    }
}
</script>

<style scoped>

</style>