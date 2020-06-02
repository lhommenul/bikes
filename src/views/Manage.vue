<template>
    <v-container id="container_manage">
        <!-- Agence -->
        <v-card class="container">
            <v-text-field
                name="name"
                label="Rechercher Une Agence"
                id="id"
            ></v-text-field>            
            <v-row>
                <v-btn color="success" @click="agence.add = true">Ajouter Une Agence</v-btn>
                <v-btn color="error">Supprimer Une Agence</v-btn>                
            </v-row>
        </v-card>
        <!-- Add User -->
        <v-card class="container">
            <v-text-field
                name="name"
                label="Rechercher Un Utilisateur"
                id="id"
            ></v-text-field>
            <v-row>
                <v-btn color="success">Ajouter Un Utilisateur</v-btn>
                <v-btn color="error">Supprimer Un Utilisateur</v-btn>                
            </v-row>                
        </v-card>      
        <!-- Add Agence -->
        <v-dialog
            v-model="agence.add"
            persistent 
            transition="dialog-transition"
        >
            <v-card>
                <v-card-title>
                    Ajouter Une Agence
                </v-card-title>
                <v-card-text>
                    <v-form>
                        <v-text-field
                         label="Nom de L'agence"
                         autofocus=true
                        />
                        <v-text-field
                         type="email"
                         label="Adresse Email"
                         autofocus=true
                        />
                        <v-text-field
                         type="number"
                         label="Numero de téléphone"
                         autofocus=true
                        />
                        <v-text-field
                         label="Adresse Postale"
                         autofocus=true
                        />      
                        <!-- Container tips -->
                        <v-container>
                            <h2>Formations Proposées</h2>
                            <v-chip-group active-class="selected" multiple>
                                <!-- Bikes -->
                                <v-chip @click="agence.type_selection.bike = !agence.type_selection.bike, days.selected = 'Moto'">Moto</v-chip>
                                <v-chip-group active-class="selected_sub" multiple v-if="agence.type_selection.bike">
                                    <v-chip>50cc</v-chip>
                                    <v-chip>125cc</v-chip>
                                    <v-chip>A2</v-chip>
                                    <v-chip>Gros Cube</v-chip>
                                </v-chip-group>
                                <!-- Cars -->
                                <v-chip @click="agence.type_selection.car = !agence.type_selection.car, days.selected = 'Voiture'">Voiture</v-chip>
                                <v-chip-group active-class="selected_sub" multiple v-if="agence.type_selection.car">
                                    <v-chip>Automatique</v-chip>
                                    <v-chip>Manuel</v-chip>
                                </v-chip-group>                                
                                <v-chip>Autre</v-chip>
                            </v-chip-group>
                        </v-container>
                        <!-- container horaire -->
                        <v-container>
                            <h2>Jours Ouverture d'Agence</h2>
                            <v-chip-group active-class="selected_sub" multiple>
                                <!-- LUNDI -->
                                <v-col>
                                    <v-chip @click="days.lundi.open = !days.lundi.open, days.selected = 'lundi', days.lundi.open_dial = !days.lundi.open_dial">Lundi</v-chip>
                                        <v-row v-if="days.lundi.open">
                                            <v-chip close v-for="item in days.lundi.hours" :key="item.id">
                                                {{ item.open }} \\
                                                {{ item.close }}
                                            </v-chip>
                                        </v-row>                                    
                                </v-col>
                                <!-- MARDI -->
                                <v-col>
                                    <v-chip @click="days.mardi.open = !days.mardi.open, days.selected = 'mardi', days.mardi.open_dial = !days.mardi.open_dial">Mardi</v-chip>
                                        <v-row v-if="days.mardi.open">
                                            <v-chip close v-for="item in days.mardi.hours" :key="item.id">
                                                {{ item.open }} \\
                                                {{ item.close }}
                                            </v-chip>                                            
                                        </v-row>                                      
                                </v-col>       
                                <!-- MERCREDI -->                   
                                <v-col>
                                    <v-chip @click="days.mercredi.open = !days.mercredi.open, days.selected = 'mercredi', days.mercredi.open_dial = !days.mercredi.open_dial">Mercredi</v-chip>
                                        <v-row v-if="days.mercredi.open">
                                            <v-chip close v-for="item in days.mercredi.hours" :key="item.id">
                                                {{ item.open }} \\
                                                {{ item.close }}
                                            </v-chip>                                            
                                        </v-row>                                         
                                </v-col>    
                                <!-- JEUDI -->                   
                                <v-col>
                                    <v-chip @click="days.jeudi.open = !days.jeudi.open, days.selected = 'jeudi', days.jeudi.open_dial = !days.jeudi.open_dial">Jeudi</v-chip>
                                        <v-row v-if="days.jeudi.open">
                                            <v-chip close v-for="item in days.jeudi.hours" :key="item.id">
                                                {{ item.open }} \\
                                                {{ item.close }}
                                            </v-chip>                                            
                                        </v-row>                                             
                                </v-col>      
                                <!-- VENDREDI -->             
                                <v-col>
                                    <v-chip @click="days.vendredi.open = !days.vendredi.open, days.selected = 'vendredi', days.vendredi.open_dial = !days.vendredi.open_dial">Vendredi</v-chip>
                                        <v-row v-if="days.vendredi.open">
                                            <v-chip close v-for="item in days.vendredi.hours" :key="item.id">
                                                {{ item.open }} \\
                                                {{ item.close }}
                                            </v-chip>                                            
                                        </v-row>        
                                </v-col>       
                                <!-- SAMEDI -->                 
                                <v-col>
                                    <v-chip @click="days.samedi.open = !days.samedi.open, days.selected = 'samedi', days.samedi.open_dial = !days.samedi.open_dial">Samedi</v-chip>
                                        <v-row v-if="days.samedi.open">
                                            <v-chip close v-for="item in days.samedi.hours" :key="item.id">
                                                {{ item.open }} \\
                                                {{ item.close }}
                                            </v-chip>                                            
                                        </v-row>                                            
                                </v-col>     
                                <!-- DIMANCHE -->               
                                <v-col>
                                    <v-chip @click="days.dimanche.open = !days.dimanche.open, days.selected = 'dimanche', days.dimanche.open_dial = !days.dimanche.open_dial">Dimanche</v-chip>
                                        <v-row v-if="days.dimanche.open">
                                            <v-chip close v-for="item in days.dimanche.hours" :key="item.id">
                                                {{ item.open }} \\
                                                {{ item.close }}
                                            </v-chip>                                            
                                        </v-row>                                   
                                </v-col>                             
                            </v-chip-group>    
                                <!-- Time Picker -->
                                <v-container v-if="days.lundi.open_dial == true | days.mardi.open_dial == true | days.mercredi.open_dial == true | days.jeudi.open_dial == true | days.vendredi.open_dial == true | days.samedi.open_dial == true | days.dimanche.open_dial == true">
                                    <v-time-picker
                                        :format="'24hr'"
                                        id="time_picker_days_open"
                                        @change="setValueClock(0,$event)"
                                    >
                                    <h3>Ouverture</h3>
                                    </v-time-picker>
                                    <!-- Fermeture -->
                                    <v-time-picker
                                        color="pink"
                                        :format="'24hr'"
                                        id="time_picker_days_close"
                                        @change="setValueClock(1,$event)"
                                    >
                                    <h3>Fermeture</h3>
                                    </v-time-picker>         
                                    <v-container>
                                        <v-btn @click="checkDial">Ajouter Horaire</v-btn>
                                    </v-container>                           
                                </v-container>                            
                        </v-container>
                        <v-btn type="submit" color="success">Ajouter</v-btn>                                          
                    </v-form>   
                </v-card-text>
            </v-card>
        </v-dialog>
    </v-container>
</template>

<script>
export default {
    data(){
        return{
            agence:{
                add:true,
                type_selection:{
                    bike:false,
                    car:false
                }
            },
            days:{
                lundi:{
                    open:false,
                    hours:[

                    ],
                    open_dial:false,
                },
                mardi:{
                    open:false,
                    hours:[

                    ],
                    open_dial:false,
                },
                mercredi:{
                    open:false,
                    hours:[

                    ],
                    open_dial:false,
                },
                jeudi:{
                    open:false,
                    hours:[

                    ],
                    open_dial:false,
                },
                vendredi:{
                    open:false,
                    hours:[

                    ],
                    open_dial:false,
                },
                samedi:{
                    open:false,
                    hours:[

                    ],
                    open_dial:false,
                },
                dimanche:{
                    open:false,
                    hours:[

                    ],
                    open_dial:false,
                },
                selected:String,
                open:String,
                close:String
            }
        }
    },
    methods: {
        setValueClock(posi,payload){
            if (posi == 0) {
                this.days.open = payload                
            } else {
                this.days.close = payload                
            }
        },
        checkDial(){
            if (this.days.open != String && this.days.close != String) {
                this.days[this.days.selected].hours.push({open:this.days.open,close:this.days.close})
                this.days.open = String;
                this.days.close = String;
            }
        }
    },
}
</script>

<style scoped>
#container_manage{
    width: 100vw;
    display: flex;
    flex-direction: row;
}
.selected_sub{
    color: white;
    background-color: rgb(12, 177, 122);
}
.selected{
    background-color: rgb(34, 143, 92);
    color: white;
}
</style>