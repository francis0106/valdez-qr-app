<template>
    <div class=" d-flex justify-center align-center"  style="height: 100vh;">
        <v-card width="500">
        <v-card-text>
            <v-form>
                <h1 style="text-align: center;">Sign In</h1>
                <br>
                <v-text-field label="Email" prepend-inner-icon="mdi-email" outlined rounded></v-text-field>
                <v-text-field label="Password" type="password" prepend-inner-icon="mdi-lock" outlined rounded></v-text-field>
                <v-btn  :loading="loading" color="blue" size="large" type="submit" variant="elevated" block rounded> Sign In</v-btn>
                <v-divider class="my-5"> <p style="text-align: center;">OR</p> </v-divider>
                
                <v-btn  :loading="loading" color="red" size="large" type="submit" variant="elevated" block rounded> Signin with Google</v-btn>
                
            </v-form>
        </v-card-text>
        </v-card>
    </div>
</template>

<script>
export default{
    layout: "auth",
}
</script>
