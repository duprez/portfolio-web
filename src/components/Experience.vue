<template>
    <div class="experience-page">
        <h1 class="main-title">{{ title }}</h1>
        <div class="formation-container">
            <div class="card-container" v-for="(item) in experience" :key="item">
               <div class="card">
                   <div class="card-content">
                       <div class="media">
                           <div>
                               <div class="media-left">
                                   <figure class="image is-48x48">
                                       <img :src="item.image">
                                   </figure>
                               </div>
                               <div class="media-content">
                                   <div class="title is-4">{{ item.company }}</div>
                                   <div class="subtitle is-6">{{ item.position }}</div>
                               </div>
                           </div>
                       </div>

                       <div class="content">
                           <div>
                               <ul class="text-list">
                                   <li v-for="text in item.texts" :key="text">{{ text }}</li>
                               </ul>
                           </div>
                           <div class="experience-date">{{ item.startDate }} - {{ item.endDate }}</div>
                           <div class="website"><a :href="item.route.path" target="_blank">{{ item.route.name }}</a></div>
                       </div>
                   </div>
               </div>
           </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Experience',
        data: function() {
            return {
                title: 'Experiencia',
                experience: [
                    {
                        company: 'CODERTY',
                        position: 'DESARROLLADOR FRONTEND',
                        startDate: 'Marzo 2018',
                        endDate: 'Febrero 2019',
                        texts: [
                            'Principales tecnologías usadas: Angular 4+, Material 4+, Ionic, NodeJS, Firebase, Vagrant, Docker.',
                            'Aspectos destacables: gestión de test unitarios en Angular, revisión de código y detección de errores.'
                        ],
                        image: require('../assets/coderty.png'),
                        route: {
                            path: 'https://www.coderty.com',
                            name: 'www.coderty.com'
                        }
                    },
                    {
                        company: 'NOA ESTUDIO',
                        position: 'DESARROLLADOR FULLSTACK',
                        startDate: 'Febrero 2019',
                        endDate: 'Abril 2020',
                        texts: [
                            'Principales tecnologías usadas: Angular, Material, NGZorro, Ionic, NodeJS, MongoDB, Amazon Web Services.',
                            'Aspectos destacables: Gestión de proyecto. Gestión y desarrollo de Amazon Web Services (Buckets, SES, SNS, Pipelines, ...).'
                        ],
                        image: require('../assets/noa_estudio.png'),
                        route: {
                            path: 'https://noaestudio.com/',
                            name: 'www.noaestudio.com'
                        }
                    }
                ]
            };
        }
    }
</script>

<style scoped lang="scss">
    @import "../styles/_variables.scss";

    .experience-page {
        padding: 15px 15px 80px;
        background-color: $foreground;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
    }
    .formation-container {
        display: flex;
        margin-top: 20px;
    }
    .card-container {
        max-width: 400px;
        padding: 20px;
        .card {
            border-radius: 12px;
            min-height: 358px;
        }
        .title, .subtitle {
            width: fit-content;
        }
        .title {
            font-size: 21px;
        }
        .subtitle {
            color: $primary-color;
            font-size: 15px;
        }
        img {
            border-radius: 100%;
        }
        .experience-date {
            margin-top: 20px;
            color: $subtitle;
        }
        .website, .experience-date {
            font-size: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .website, .website > a, .website > a:hover {
            color: $primary-color;
        }
        .media {
            display: flex;
            align-items: center;
            justify-content: center;
            & > div {
                display: flex;
                align-items: center;
                justify-content: center;
            }
            .media-content {
                overflow: hidden;
            }
        }
        .text-list {
            color: $alternative-font;
            font-size: 14px;
            li {
                padding: 7px 0;
            }
        }
    }

    @media (max-width: $lg) {
        .formation-container {
            display: block;
        }
    }

    @media (max-width: $xs) {
        .experience-page {
            padding: 30px 0;
            .formation-container {
                display: block;
                width: 100%;
            }
            .card-container {
                width: 100%;
                max-width: 100%;
                padding: 0;
                .card {
                    border-radius: 0;
                }
            }
        }
    }
</style>