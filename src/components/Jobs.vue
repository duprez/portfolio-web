<template>
    <div class="jobs-page">
        <h1 class="main-title">{{ title }}</h1>
        <div class="subtitle">{{ subtitle }} <a class="email-text" :href="'mailto: ' + email">{{ emailText }}</a></div>
        <div class="jobs-container">
            <div class="card job-block" v-for="job in jobs" :key="job" :style="getCardBackground(job)"  @mouseover="job.displayDesc = true" @mouseleave="job.displayDesc = false">
                <div class="foreground" :style="getCardForeground(job)"></div>
                <div class="job-footer">{{ job.title }}</div>

                <transition name="fade">
                    <div v-if="job.displayDesc" class="card-reverse">
                        <div class="project-desc">{{ job.projectDesc }}</div>
                        <b-button
                                type="is-primary"
                                rounded
                                outlined
                                @click="openLink(job.link)"
                        >
                            Ver sitio
                            <i class="fas fa-chevron-right"></i>
                        </b-button>
                    </div>
                </transition>
            </div>
        </div>
        <div class="github-button">
            <b-button
                    type="is-primary"
                    rounded
                    outlined
                    @click="openGithub()"
            >
                Ver GitHub
                <i class="fab fa-github"></i>
            </b-button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Jobs',
        data: function() {
            return {
                title: 'Mis trabajos',
                subtitle: 'Aquí están algunos de mis trabajos. ¿Quieres ver más?',
                emailText: 'Envíame un email',
                email: 'antonioduprezher@gmail.com',
                jobs: [
                    {
                        title: 'Formación HUPHM',
                        background: require('../assets/huphm.jpg'),
                        foreground: '#4848C5',
                        foregroundTransparency: '60%',
                        author: 'HUPHM MAJADAHONDA',
                        projectDesc: 'Desarrollador Fullstack usando ionic y nodejs. Aplicación para la formación continuada. Esta aplicación tiene cursos, píldoras formativas, sesiones, noticias, ...',
                        displayDesc: false,
                        link: 'https://play.google.com/store/apps/details?id=com.seasalt.huphmlearning&hl=es'
                    },
                    {
                        title: 'IFAPA',
                        background: require('../assets/ifapa.jpg'),
                        foreground: '#AEC159',
                        foregroundTransparency: '49%',
                        author: 'JUNTA DE ANDALUCÍA',
                        projectDesc: 'Desarrollador Frontend usando ionic como tecnología principal. Es una aplicación para la consulta de plagas, enemigos naturales y virus para la Consejería de Agricultura y Pesca.',
                        displayDesc: false,
                        link: 'https://play.google.com/store/apps/details?id=es.juntadeandalucia.ifapa.guia&hl=es'
                    },
                    {
                        title: 'ALDETRANS',
                        background: require('../assets/aldetrans.jpg'),
                        foreground: '#944141',
                        foregroundTransparency: '70%',
                        author: 'CODERTY',
                        projectDesc: 'Desarrollador Frontend usando ionic como tecnología principal. Es una aplicación para la gestión interna de la empresa: clientes, proveedores, productos, envíos, logística, etc.',
                        displayDesc: false,
                        link: 'https://play.google.com/store/apps/details?id=com.codertysl.aldetrans&hl=es_CO'
                    },
                    {
                        title: 'PPI UAL',
                        background: require('../assets/ual.jpg'),
                        foreground: '#6F3A1F',
                        foregroundTransparency: '45%',
                        author: 'NOA ESTUDIO',
                        projectDesc: 'Desarrollador backend usando nodejs, mongodb y typeorm. Es una web para la gestión y concensión de solicitudes predoctorales en la Universidad de Almería.',
                        displayDesc: false,
                        link: 'https://ppi.ual.es/#/login'
                    }
                ]
            };
        },
        methods: {
            getCardBackground(job) {
                return {
                    backgroundImage: 'url(' + job.background + ')',
                }
            },
            getCardForeground(job) {
                return {
                    backgroundColor: job.foreground,
                    opacity: job.foregroundTransparency
                }
            },
            openLink(link) {
                window.open(link);
            },
            openGithub() {
                window.open('https://github.com/duprez');
            }
        }
    }
</script>

<style scoped lang="scss">
    @import "../styles/_variables.scss";
    $card-border: 12px;
    $subtitle-color: #141C3A;
    $card-background: #141B39;

    .main-title {
        padding-bottom: 15px;
    }
    .jobs-page {
        min-height: 100vh;
        padding-top: 60px;
        .subtitle {
            text-align: center;
            color: $subtitle-color;
            font-size: 16px;
            margin-bottom: 70px;
            padding: 0 20px;
            .email-text {
                color: $primary-color;
            }
        }

        .jobs-container {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-wrap: wrap;
            max-width: 80%;
            margin: 0 auto;
            .job-block {
                height: 200px;
                width: 300px;
                border-radius: $card-border;
                background-repeat: no-repeat;
                background-size: cover;
                margin: 0 40px 80px;
                .foreground {
                    height: 100%;
                    width: 100%;
                    border-radius: $card-border;
                }
            }
            .job-footer {
                background-color: $card-background;
                color: $primary-color;
                border-radius: 0 0 $card-border $card-border;
                padding: 10px 20px;
                position: relative;
                bottom: 25px;
                text-align: center;
            }
            .card-reverse {
                background-color: $card-background;
                position: relative;
                bottom: 245px;
                height: 205px;
                padding: 20px;
                border-radius: 12px;
                text-align: center;
                .project-desc {
                    color: #ffffff;
                    font-size: 15px;
                    text-align: center;
                }
                button {
                    margin-top: 20px;
                }
            }
        }
        .github-button {
            text-align: center;
            padding: 20px 0 70px;
            button {
                font-size: 17px;
            }
        }
    }

    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s;
    }
    .fade-enter, .fade-leave-to {
        opacity: 0;
    }

    @media (max-width: $lg) {
        .jobs-page > .jobs-container {
            max-width: 100%;
        }
    }
</style>