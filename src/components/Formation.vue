<template>
    <div class="formation-page">
        <div class="formation-page-container">
        </div>
        <div class="main-content">
            <h1 class="main-title">{{ title }}</h1>
            <div class="card formation-container">
                <div class="card-content">
                    <div class="formation-block" v-for="item in formation" :key="item">
                        <img class="image" :src="item.icon">
                        <h3>{{ item.title }}</h3>
                        <div class="description">
                            {{ item.description }}
                        </div>
                        <h4 class="subtitle">{{ item.subtitle }}:</h4>
                        <div class="tools">
                            <div class="tool" :class="{ 'academic-degrees': item.academicDegrees }" v-for="characteristic in item.characteristics" :key="characteristic">
                                {{ characteristic }}
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Formation',
        data: function() {
            return {
                title: 'Formación',
                formation: [
                    {
                        title: 'Frontend Developer',
                        description: 'Me encanta trabajar con tecnologías que permitan la reutilización de código y poder  estructurarlo de forma organizada y limpia.',
                        subtitle: 'Herramientas',
                        characteristics: [
                            'Angular',
                            'Ionic',
                            'VueJS',
                            'Sass/Scss',
                            'Bootstrap',
                            'Material',
                            'NgZorro',
                            'Jquery',
                            'Adobe XD'
                        ],
                        icon: require('../assets/frontend_developer.svg')
                    },
                    {
                        title: 'Backend Developer',
                        description: 'Me gusta analizar con tranquilidad todas las alternativas posibles para un desarrollo y llevarlo a cabo con todas las herramientas disponibles.',
                        subtitle: 'Herramientas',
                        characteristics: [
                            'NodeJS',
                            'TypeORM',
                            'MongoDB',
                            'AWS',
                            'SQL/NoSQL',
                            'NestJS',
                            'Datagrip',
                            'Workbench',
                            'Firebase',
                            'PHP'
                        ],
                        icon: require('../assets/backend_developer.svg')
                    },
                    {
                        title: 'Formación académica',
                        description: 'Me apasiona el mundo de las tecnologías, me gusta formarme continuamente haciendo diversos cursos sobre tecnologías diferentes.',
                        subtitle: 'Titulación',
                        characteristics: [
                            'Técnico Superior en Desarrollo de Aplicaciones Web',
                            'Enseñanza de Inglés como Lengua Extranjera (Nivel A2)',
                            'Bachillerato de Ciencias Sociales'
                        ],
                        icon: require('../assets/academic_degree.svg'),
                        academicDegrees: true
                    }
                ]
            };
        }
    }
</script>

<style scoped lang="scss">
    @import "../styles/_variables.scss";

    .formation-page {
        min-height: 100vh;
        width: 100vw;
        .main-title {
            padding-bottom: 50px;
        }
        .formation-page-container {
            height: 60vh;
            background-color: $foreground;
        }
        .main-content {
            margin-top: -60vh;
        }
        .formation-container {
            background-color: #ffffff;
            border-radius: 12px;
            max-width: 80%;
            margin: 0 auto;
        }
        .card-content {
            display: flex;
            justify-content: center;
            padding: 0;
            .formation-block {
                display: flex;
                flex-direction: column;
                align-items: center;
                padding: calc(1.5rem + 20px) 30px 15px;
                &:not(:last-child) {
                    border-right: solid 1px $border;
                }
                .image {
                    width: 31px;
                    height: 35px;
                }
                h3 {
                    font-size: 21px;
                    font-weight: 500;
                    padding: 12px 0 20px;
                    text-align: center;
                }
                .description {
                    color: $alternative-font;
                    font-size: 14px;
                    padding-bottom: 30px;
                    text-align: center;
                }
                .subtitle {
                    color: $primary-color;
                    font-size: 19px;
                }
                .tools {
                    line-height: 2;
                    font-size: 14px;
                    text-align: center;
                }
                .academic-degrees {
                    padding: 10px 0;
                }
            }
        }
    }

    @media (max-width: $md) {
        .formation-page {
            padding-top: 0;
            .formation-container {
                max-width: 100%;
            }
        }
    }

    @media (max-width: $xs) {
        .formation-page {
            padding-top: 0;
            .formation-container {
                .card-content {
                    flex-direction: column;

                    .formation-block {
                        border-bottom: solid 1px $border;
                    }
                }
            }
        }
    }
</style>