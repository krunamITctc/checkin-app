<template>
    <v-container grid-list-xl>
        <v-layout column>
        <v-flex xs12>
        <h1 class="title">Register</h1>
        </v-flex>
        <v-flex xs12 sm12><v-text-field v-model="user" label="Username:"></v-text-field> </v-flex>
        <v-flex >          
            <v-layout>
                <v-flex xs6><v-text-field v-model="pass" label="Password:" type="password"></v-text-field> </v-flex>
                <v-flex x6> <v-text-field v-model="pass2" label="Password Confrim:" type="password"> 
                </v-text-field> </v-flex> 
            </v-layout>
            
        </v-flex>          
         <v-flex xs12><v-btn @click="register"> <v-icon>account_circle</v-icon> Login</v-btn></v-flex>   
        </v-layout>
    </v-container>
</template>
<script>
export default {
    layout:'login',
    data(){
        return {
             user: '',
             pass: '',
             pass2: '',
        }
    },
    methods:{
        register(){

        },
    },
}
</script>
