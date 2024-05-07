<script>
    export default { 
        methods: {
            goToLink(link) {
                window.open(link, '_blank');
            },
        },

    }
</script>

<template>
    <v-container fluid class="pa-0 ma-0">
        <v-row class="bg-grey-darken-4 pa-10">
            <v-col justify="center" align="center" class="pa-0 pt-5">
                <v-row class="mb-1" justify="center" align="center">
                    <v-avatar color="white" size="35" class="mr-1"><v-text class="font-weight-medium text-black">&lt;/&gt;</v-text></v-avatar>
                    <p class="text-h6 font-weight-bold">JuanFourThree</p>
                </v-row>
                <v-row justify="center" align="center" class="my-4 ga-2">
                    <v-btn variant="tonal" icon="mdi-linkedin" @click="goToLink('https://www.linkedin.com/in/john-carlo-7b18552a0')"></v-btn>
                    <v-btn variant="tonal" icon="mdi-facebook" @click="goToLink('https://www.facebook.com/johncarlo.paz.75')"></v-btn>
                    <v-btn variant="tonal" icon="mdi-github" @click="goToLink('https://github.com/John-CarloPaz')"></v-btn>
                </v-row>
                <p>Designed and Built by John Carlo Paz</p>
                <p>Copyright © 2024 - All Rights Reserved</p>
            </v-col>
        </v-row>
    </v-container>
</template>