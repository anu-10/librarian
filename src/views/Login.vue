<template>
        <div class="center">
            <v-row>
                <v-col cols="10" offset="1" offset-sm="3" md="4" offset-md="4">
                    <v-avatar
                    color="primary"
                    size="97" tile
                    >
                    <v-img src="../assets/logo.png"></v-img>
                    </v-avatar><br>
                    <v-text-field
                        label="Username"
                        placeholder="Enter your username" v-model="username"
                    ></v-text-field>
                    <v-text-field type="password"
                        label="Password"
                        placeholder="Enter your password"
                        v-model="password"
                    ></v-text-field>
                <v-btn class = "base-inverted" block @click="authenticate()">
                    Login
                </v-btn>  
                </v-col>
            </v-row>
        </div>
          
</template>

<script>
    export default {
        data(){
            return {
                username: "",
                password: ""
            }
        },
        methods:
        {
            authenticate()
            {
                if(this.username=="" || this.username=="")
                    alert("Fields cannot be Empty.")
                else
                    alert("Login successful.")
            }
        }
    }
</script>

<style lang="scss" scoped>
</style>