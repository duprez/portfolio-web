<template>
    <div class="cover-page">
        <div class="left-side">
            <div class="cover-solid">
                <div class="title-container">
                    <h3 class="main-title">Hola, soy {{ name }}</h3>
                    <hr>
                </div>
                <div class="about-me">
                    <p v-for="text in paragraphs" :key="text">
                        {{ text }}
                    </p>
                </div>
            </div>
        </div>
        <div class="right-side">
            <div class="cover-image"></div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CoverPage',
        data: function() {
            return {
                name: 'Antonio Duprez',
                paragraphs: [
                    'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis sagittis facilisis tortor sed iaculis. Vivamus id est metus. Curabitur luctus erat porta, rhoncus ex nec, imperdiet risus. Duis convallis scelerisque porta. Vestibulum eget metus nec magna luctus consequat. Curabitur sit amet risus pretium.',
                    'Semper tellus et, gravida nibh. Nulla facilisis auctor purus, eget sodales nisl pellentesque in. Sed consectetur varius tortor blandit convallis. Cras nunc dolor, laoreet et tempus at, dapibus non lectus'
                ]
            };
        }
    }
</script>

<style scoped lang="scss">
    @import "../styles/_variables.scss";
    .cover-page {
        display: flex;
        background-color: $background-color;
    }
    .left-side, .right-side {
        width: 50%;
    }
    .cover-solid {
        height: 100vh;
        width: 100%;
        background-color: $background-color;
        opacity: 1;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        padding: 35px;
    }
    .cover-image {
        height: 100vh;
        width: 100%;
        background-image: url("../assets/me.jpg");
        background-repeat: no-repeat;
        background-size: cover;
        background-position: 50% 50%;
        clip-path: polygon(20% 0, 100% 0%, 100% 100%, 0% 100%);
        opacity: 1;
    }
    .title-container {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .main-title {
        color: $title-color;
        font-size: 25px;
    }
    hr {
        width: 110px;
        background-color: $primary-color;
        margin: 15px;
    }
    .about-me {
        color: $font-color;
        p {
            margin: 30px 0;
        }
    }

    @media (max-width: $lg) {
        .left-side {
            width: 100%;
        }
        .right-side {
            width: 0;
        }
    }

    @media (max-width: $md) {
        .title-container {
            flex-direction: column;
        }
        hr {
            width: 100%;
        }
    }
</style>