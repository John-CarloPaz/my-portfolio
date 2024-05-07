<script>
import Footer from '../components/footer_component.vue';
    export default {
        components: {
            Footer,
        },
        methods: {
            goToLink(email) {
                const subject = encodeURIComponent("RE: New Project Inquiry");
                const body = encodeURIComponent("I'd like to chat about a new project. I am [Your Name] and I am interested in working with you. Here are some details about the project: [Project Details]");
                const url = `https://mail.google.com/mail/u/0/?view=cm&fs=1&to=${email}&su=${subject}&body=${body}`;
                window.open(url, '_blank');
            },
        }
    };
</script>

<template>
    <v-container fluid class="ma-0 pa-0">
        <v-row class="bg-blue-grey-darken-4" style="min-height: 100vh;" justify="center"> <!-- Parent -->
            <v-col cols="10" class="mt-16" justify="center" align="center"> 
                <v-row class="mt-16 pt-16" justify="center" align="center">
                    <v-col cols="12" lg="9" md="9">
                        <p class="text-h6 text-sm-h5 text-md-h4 text-lg-h4">I'm currently open to exciting new projects, both part-time and freelance! Feel free to reach out and say hello, I'd love to chat!</p>
                        <v-btn variant="outlined" class="text-h6 mt-6" size="x-large"  @click="goToLink('jpaz.20221027@gmail.com')">Say Hi! <v-icon icon="mdi-send" class="ml-2"></v-icon></v-btn>
                    </v-col>

                    <v-col cols="12" class="align-self-bottom">
                        <v-img :src="require('../assets/laptop.png')"  alt="workstation" max-width="600"></v-img>
                    </v-col>
                </v-row>
            </v-col> 
        </v-row> <!-- Parent -->
        <footer>
            <Footer/>
        </footer>
    </v-container>
</template>