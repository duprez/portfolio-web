<template>
  <div id="app">
    <CoverPage></CoverPage>
    <Experience></Experience>
    <Formation></Formation>
    <Jobs></Jobs>
    <Footer></Footer>
  </div>
</template>

<script>
import CoverPage from './components/CoverPage';
import Experience from './components/Experience';
import Formation from './components/Formation';
import Jobs from './components/Jobs';
import Footer from './components/Footer';


export default {
  name: 'App',
  components: {
    CoverPage,
    Experience,
    Formation,
    Jobs,
    Footer
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Titillium+Web:ital,wght@0,400;1,300&display=swap');
  @import "styles/_bulma.scss";


  #app {
    font-family: 'Titillium Web', sans-serif;
  }
  body {
    margin: 0;
  }
  .main-title {
    width: fit-content;
    margin: 0 auto;
    font-size: 32px;
    padding-top: 15px;
    padding-bottom: 30px;
    font-weight: bold;
    color: #141b39;
  }
</style>
