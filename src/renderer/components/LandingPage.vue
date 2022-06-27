<template>
  <div id="wrapper" class="relay2">
<!--    <img id="logo" src="~@/assets/logo.png" alt="electron-vue">-->
<!--    <main>-->
<!--      <div class="left-side">-->
<!--        <span class="title">-->
<!--          Welcome to your new project!-->
<!--        </span>-->
<!--        <system-information></system-information>-->
<!--      </div>-->

<!--      <div class="right-side">-->
<!--        <div class="doc">-->
<!--          <div class="title">Getting Started</div>-->
<!--          <p>-->
<!--            electron-vue comes packed with detailed documentation that covers everything from-->
<!--            internal configurations, using the project structure, building your application,-->
<!--            and so much more.-->
<!--          </p>-->
<!--          <button @click="open('https://simulatedgreg.gitbooks.io/electron-vue/content/')">Read the Docs</button><br><br>-->
<!--        </div>-->
<!--        <div class="doc">-->
<!--          <div class="title alt">Other Documentation</div>-->
<!--          <button class="alt" @click="open('https://electron.atom.io/docs/')">Electron</button>-->
<!--          <button class="alt" @click="open('https://vuejs.org/v2/guide/')">Vue.js</button>-->
<!--        </div>-->
<!--      </div>-->
<!--    </main>-->
    <div class="columns">
      <div class="column is-half">
        <vue-plyr>
          <div class="plyr__video-embed">
            <iframe
                src="https://www.youtube.com/embed/eOMhOjgNd7Q?autoplay=1&controls=0&loop=1&controls=0"
                allowfullscreen
                allowtransparency
                allow="autoplay"
            ></iframe>
          </div>
        </vue-plyr>
      </div>
      <div class="column is-half">
        <p>Ads</p>
      </div>
    </div>
    <div class="columns">
      <div class="column is-half">
        <p>Ads</p>
      </div>
      <div class="column is-half">
        <vue-plyr :options="options">
          <video>
            <source
                src="~@/assets/ad1.mp4"
                type="video/mp4"
            />
          </video>
        </vue-plyr>
      </div>
    </div>
  </div>
</template>

<script>
  import SystemInformation from './LandingPage/SystemInformation'

  export default {
    name: 'landing-page',
    components: { SystemInformation },
    methods: {
      open (link) {
        this.$electron.shell.openExternal(link)
      }
    }
  }
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro');

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body { font-family: 'Source Sans Pro', sans-serif; }

  .plyr__controls {
    display: none !important;
  }

  #wrapper {
    height: 100vh;
    padding: 0;
    //width: 100vw;
  }

  .relay2 {
    .column {
      background-color: #c6c6c6;
      padding: 0;
      p {
        margin-top: 30%;
        text-align: center;
        font-weight: 700;
      }
    }
  }

  #logo {
    height: auto;
    margin-bottom: 20px;
    width: 420px;
  }

  main {
    display: flex;
    justify-content: space-between;
  }

  main > div { flex-basis: 50%; }

  .left-side {
    display: flex;
    flex-direction: column;
  }

  .welcome {
    color: #555;
    font-size: 23px;
    margin-bottom: 10px;
  }

  .title {
    color: #2c3e50;
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 6px;
  }

  .title.alt {
    font-size: 18px;
    margin-bottom: 10px;
  }

  .doc p {
    color: black;
    margin-bottom: 10px;
  }

  .doc button {
    font-size: .8em;
    cursor: pointer;
    outline: none;
    padding: 0.75em 2em;
    border-radius: 2em;
    display: inline-block;
    color: #fff;
    background-color: #4fc08d;
    transition: all 0.15s ease;
    box-sizing: border-box;
    border: 1px solid #4fc08d;
  }

  .doc button.alt {
    color: #42b983;
    background-color: transparent;
  }
</style>
