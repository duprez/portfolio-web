<template>
    <div class="footer-page">
        <div class="footer-container">
            <div class="logos">
                <a class="logo-container" :href="twitter" target="_blank">
                    <i class="fab fa-twitter"></i>
                </a>
                <a class="logo-container" :href="linkedIn" target="_blank">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a class="logo-container" :href="'mailto:' + email" target="_blank">
                    <i class="far fa-envelope"></i>
                </a>
            </div>
            <div class="pixabay">
                <i class="fas fa-camera-retro"></i>
                <span>Images by <a href="https://pixabay.com/es/" target="_blank" class="link">Pixabay</a></span>
            </div>
            <div class="made-with">
                Made with <i class="fab fa-vuejs"></i> <a href="https://vuejs.org/" target="_blank" class="link">VueJS</a>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Footer',
        data: function() {
            return {
                twitter: 'https://twitter.com/duprez26',
                linkedIn: 'https://es.linkedin.com/in/antonio-duprez-hern%C3%A1ndez-194670157',
                email: 'antonioduprezher@gmail.com'
            };
        }
    }
</script>

<style scoped lang="scss">
    @import "../styles/_variables.scss";

    .link:hover {
        color: $primary-color;
    }
    .footer-page {
        background-color: $background-color;
        color: #ffffff;
        .footer-container {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            height: 200px;
            .logos {
                display: flex;
                flex-direction: row;
                padding: 10px 0;
                .logo-container {
                    margin: 10px;
                    font-size: 21px;
                    border: solid 1px #ffffff;
                    border-radius: 50%;
                    height: 42px;
                    width: 42px;
                    cursor: pointer;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    color: #ffffff;
                    &:hover {
                        background-color: gray;
                    }
                }
            }

            .pixabay {
                color: $primary-color;
                padding: 7px 0;
                .fa-camera-retro {
                    margin-right: 7px;
                }
            }
            .made-with {
                color: $primary-color;
                font-size: 13px;
            }
        }
    }
</style>