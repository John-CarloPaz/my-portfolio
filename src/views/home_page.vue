<script>
import Footer from '../components/footer_component.vue';
    export default {
        data() {
            return {
                frontendSkills: [
                    { name: 'HTML', icon: 'mdi-language-html5' },
                    { name: 'CSS', icon: 'mdi-language-css3' },
                    { name: 'JavaScript', icon: 'mdi-language-javascript' },
                    { name: 'Vue.js', icon: 'mdi-vuejs' },
                    { name: 'Vuetify', icon: 'mdi-vuetify' },
                    { name: 'React Native', icon: 'mdi-react' },
                    {name: 'Flutter', icon: 'mdi-cellphone'},
                    { name: 'Bootstrap', icon: 'mdi-bootstrap' }, 
                    { name: 'Axios', icon: 'mdi-link-circle' }, 
                    { name: 'Git', icon: 'mdi-git' }, 
                ],
                backendSkills: [
                    { name: 'Laravel', icon: 'mdi-laravel' },
                    { name: 'PHP', icon: 'mdi-laravel' },
                    { name: 'MySQL', icon: 'mdi-database' },
                    { name: 'Node.js', icon: 'mdi-nodejs' },
                    { name: 'Firebase', icon: 'mdi-firebase' },
                    { name: 'Git', icon: 'mdi-git' },
                ],
            };
        },
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
    <v-container  class="pa-0 ma-0" fluid>
        <v-row class="pa-0 ma-0">
            <v-col cols="12" class="pa-0 ma-0" style="min-height: 100vh;">
                <v-row justify="center" align="center" class="pa-0 ma-0" style="background: radial-gradient(circle, rgba(117,95,184,1) 0%, rgba(49,27,146,1) 100%); background-size: 100% 100%; height: 100%; transform: translateZ(0);">
                    <v-col class="pa-0 ma-0 pt-10 pt-lg-0 pt-md-0" cols="10" style="height: 100%;"> 
                        <v-row justify=center align="center" class="pa-0 ma-0 pt-10 pt-lg-0 pt-md-0" style="height: 100%;">
                            <v-col  cols="12" lg="5" md="6" class="mt-10 pt-10 pt-lg-0 pt-md-0" >
                                <p class="text-white text-h5 text-sm-h4 text-md-h4 text-lg-h3 text-align-start text-left">Learning. Building. Growing. | A Student Developer on a Journey</p>
                                <p class="text-white text-subtitle-2 d-block my-3 text-left">Hello, I am <strong class="text-white">John Carlo Paz</strong>. Leveraging Laravel, Vue.js, MySQL & React Native to Craft Engaging User Experiences.</p>
                                <v-btn variant="elevated" color="deep-purple-lighten-5 mr-10" size="large"><v-text class="text-deep-purple-darken-4"  @click="goToLink('jpaz.20221027@gmail.com')">Contact Me</v-text></v-btn>
                            </v-col>
                            <v-col cols="12" lg="6" md="7" class="pa-0 ma-0 align-self-end" justify="center" align="center" style="background: radial-gradient(circle, rgba(245,202,255,0.5) 5%, rgba(145,254,255,0) 70%); border-radius: 100%; transform: translateZ(0);">
                                <v-img :src="require('../assets/jpaz.png')" alt="John Carlo Paz Image" style="width: 80%;"></v-img>
                            </v-col>
                        </v-row>
                    </v-col>
                </v-row>
            </v-col>
            
            <v-col cols="12">
                <v-row justify="center" align="center" class="bg-blue-grey-darken-4">
                    <v-col cols="10">
                        <v-row justify="center" align="center" class="mt-5">
                            <v-col cols="12" class="mt-5">
                                <v-row  justify="center" align="center" class="mt-10">
                                    <v-col cols="12" class="mt-10 pa-0" justify="start" align="start">
                                        <p class="text-start font-weight-bold text-h5 text-lg-h4 text-md-h4">Featured Skills</p>
                                    </v-col>
                                    <v-col  cols="12" align="center">
                                        <p class="text-h6 text-lg-h5 text-md-h5 font-weight-bold mb-1">Frontend</p>
                                    </v-col>
                                    <v-row justify="center" align="center" class="mb-5">
                                        <v-chip v-for="(frontendSkill, index) in frontendSkills" :key="index" class="mx-1 my-1" variant="outlined" size="x-large" color="deep-purple-lighten-5" text-color="deep-purple-darken-1">
                                            <v-icon class="mr-1" :icon="frontendSkill.icon"></v-icon>
                                            {{ frontendSkill.name }}
                                        </v-chip>
                                    </v-row>
                                    <v-col cols="12" align="center">
                                        <p class="text-h6 text-lg-h5 text-md-h5 font-weight-bold mb-1">Backend</p>
                                    </v-col>
                                    <v-row justify="center" align="center" class="mb-16">
                                        <v-chip v-for="(backendSkill, index) in backendSkills" :key="index" class="mx-1 my-1" variant="outlined" size="x-large" color="deep-purple-lighten-5" text-color="deep-purple-darken-1">
                                            <v-icon class="mr-1" :icon="backendSkill.icon"></v-icon>
                                            {{ backendSkill.name }}
                                        </v-chip>
                                    </v-row>
                                </v-row>
                            </v-col>

                            <v-col cols="12" class="rounded-lg bg-grey-darken-4 d-flex align-center my-16">
                                <v-row justify="start" align="center">
                                    <v-col cols="12" lg="3" md="6" sm="5" class="rounded mx-auto" >
                                        <v-img class="w-100" :src="require('../assets/robot.png')"
                                        v-motion
                                        :initial="{
                                            y: 0
                                        }"
                                        :enter="{
                                            y: 20,
                                            transition: {
                                                repeat: Infinity,
                                                repeatType: 'reverse',
                                                type: 'spring',
                                                stiffness: 20,
                                                mass: 2,
                                            },
                                        }"
                                        ></v-img>
                                    </v-col>
                                    <v-col cols="12" lg="9" class="rounded mx-auto pa-8">
                                        <p class="text-h5 font-weight-bold text-h5 text-lg-h4 text-md-h4 text-deep-purple-accent-2 my-5">About Me</p>
                                        <p class="text-body-1 mb-2 text-justify">Hello, I am John Carlo Paz a highly motivated student developer passionate about building innovative web & mobile apps.  Fueled by a strong foundation in CS (BS IT - Mobile Dev at Systems Plus) and a love for tackling challenges.</p>
                                        <p class="text-body-1 text-justify">I bring technical expertise (Laravel, Vue.js, MySQL, React Native) and strong communication/problem-solving skills to collaborate effectively and create impactful projects.</p>
                                    </v-col>
                                </v-row>
                            </v-col>

                        </v-row>
                    </v-col>
                </v-row>
            </v-col>
        </v-row>
        <footer>
            <Footer/>
        </footer>
    </v-container>
</template>

 
<style>
* {
    font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color: #BDBDBD;
}
</style>