<script>
import Footer from '../components/footer_component.vue';


    export default { 
        data() { 
            return { 
                isHovered: false,
                isHoveredCertificates: false,
                projects: [
                    { title: 'Marvin Technical Services | Dubai', description: 'Landing page for handyman & cleaning.', image: require('../assets/techserv.jpeg'), link: 'https://marvintechnicalservices.com' },
                    { title: 'ICP Hackathon Entry: Parkbnb', description: 'Landing page for Parkbnb, parking app.', image: require('../assets/icp.png'), link: 'https://gfoqp-6qaaa-aaaao-a3kua-cai.icp0.io/' },
                    { title: 'Ease Swap | UI/UX Design', description: 'User interface for item swapping app.', image: require('../assets/easeswap.png'), link: 'https://www.figma.com/file/GYS8oiwP3CSsma5U7IAvZ0/EaseSwap?type=design&node-id=115%3A527&mode=design&t=FFMTIEBlmu1Cq0aJ-1' },
                ],
                certificates: [
                    { title: 'Information Technology Specialist in Databases', description: 'Certified ITS in Databases by Certiport',  image: require('../assets/certdatabses.png'), link: 'https://www.certiport.com/portal/pages/credentialverification.aspx' },
                    { title: 'HTML, CSS, Javascript for Web Developers | Coursera', description: 'Coursera cetificate of accomplisment', image: require('../assets/certhtml.png'), link: 'https://coursera.org/share/e2cad8eabeb9d89326b43ff88ef4220c' },
                    { title: 'Introduction to Java', description: 'Coursera cetificate of accomplisment', image: require('../assets/certjava.png'), link: 'https://coursera.org/share/e073cde29b8e178b0ac7513fc80ff57d' },
                ],
            };
        },
        created() {
            this.isHovered = this.projects.map(() => false);
            this.isHoveredCertificates = this.certificates.map(() => false);
        },
        components: {
            Footer,
        },
        methods: {
            goToLink(link) {
                window.open(link, '_blank');
            },
        },
    };
</script>

<template>
<v-container fluid class="pa-0">
    <v-row>
        <v-col cols="12">
            <v-row justify="center" class="bg-blue-grey-darken-4" style="min-height: 100vh;">
                <v-col cols="10" lg="8" justify=center align=center class="mt-16">
                    <v-row justify="start" align="center" class="mt-16 pa-8 pa-lg-16 pa-md-16 pa-sm-16 bg-grey-darken-4 rounded-lg d-flex align-stretch">
                        <v-col cols="12" class="ml-2">
                            <v-row>
                                 <v-icon icon="mdi-file" class="mr-2"></v-icon>
                                 <p class="text-start font-weight-bold text-h5 text-lg-h4 text-md-h4">Featured Projects</p>
                            </v-row>
                        </v-col>
                        <v-col v-for="(project, index) in projects" :key="index" cols="12" lg="4" md="4" sm="6">
                            <v-card class="w-100 d-flex flex-column my-card" color="blue-grey-darken-4" elevation="8" :class="{'hovered': isHovered[index]}" @mouseover="isHovered[index] = true" @mouseleave="isHovered[index] = false" @click="goToLink(project.link)">
                                <v-img :height="200" :src="project.image" :alt="project.title" cover></v-img>
                                <v-card-title class="text-start">{{ project.title }}</v-card-title>
                                <v-card-text class="text-start flex-grow-1">{{project.description}}</v-card-text>
                            </v-card>
                        </v-col>
                    </v-row>
                </v-col>

                <v-col cols="10" lg="8" justify=center align=center class="my-16">
                    <v-row justify="start" align="center" class="mt-16 pa-8 pa-lg-16 pa-md-16 pa-sm-16 bg-grey-darken-4 rounded-lg d-flex align-stretch">
                        <v-col cols="12" class="ml-2">
                            <v-row>
                                 <v-icon icon="mdi-certificate" class="mr-2"></v-icon>
                                 <p class="text-start font-weight-bold text-h5 text-lg-h4 text-md-h4">Certifications</p>
                            </v-row>
                        </v-col>
                        <v-col v-for="(certificate, index) in certificates" :key="index" cols="12" lg="4" md="4" sm="6">
                            <v-card class="w-100 d-flex flex-column my-card" color="blue-grey-darken-4" elevation="8" :class="{'hovered': isHoveredCertificates[index]}" @mouseover="isHoveredCertificates[index] = true" @mouseleave="isHoveredCertificates[index] = false" @click="goToLink(certificate.link)">
                                <v-img :height="200" :src="certificate.image" :alt="certificate.title" cover></v-img>
                                <v-card-title class="text-start">{{ certificate.title }}</v-card-title>
                                <v-card-text class="text-start flex-grow-1">{{certificate.description}}</v-card-text>
                            </v-card>
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

<style scoped>
.my-card {
  transition: all 0.3s ease;
}

.my-card.hovered {
  transform: scale(1.05);
  cursor: pointer;
}
</style>

