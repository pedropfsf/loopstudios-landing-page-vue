<template>
  <div id="run">
    <Background
      :typeJustifyContent="
        valueMenuMobile ? 'flex-start' : 'space-between'
      "
      :removeBackgroundImage="valueMenuMobile"
    >
      <Header
        :valueMenuMobile="valueMenuMobile"
        :methodMenuMobile="changeMenuMobile"
      />
      <MenuMobile
        v-show="valueMenuMobile"
      />
      <MessageText
        v-show="!valueMenuMobile"
      >
        IMMERSIVE EXPERIENCES THAT DELIVER
      </MessageText>
    </Background>
    
    <Main
      v-show="!valueMenuMobile"
    />
    <Footer
      v-show="!valueMenuMobile"
    />
  </div>
</template>

<script>

  import Background from './components/Background/Background.vue';
  import Header from './components/Header/Header.vue';
  import MessageText from './components/MessageText/MessageText.vue';
  import Main from './components/Main/Main.vue';
  import Footer from './components/Footer/Footer.vue';
  import MenuMobile from './components/MenuMobile/MenuMobile.vue';

export default {
    name: 'App',
    components: {
      Background,
      Header,
      MessageText,
      Main,
      Footer,
      MenuMobile
    },
    data() {
      return {
        valueMenuMobile: false,
        mediaQuerieList: matchMedia("(max-width: 822px)")
      }
    },
    methods: {
      changeMenuMobile() {
        this.valueMenuMobile = !this.valueMenuMobile;
      },
      changeValueResponsive(mediaQuerieList) {
        if(!mediaQuerieList.matches) {
          this.valueMenuMobile = false;
        }
      }
    },
    mounted() {
      this.changeValueResponsive(this.mediaQuerieList);

      this.mediaQuerieList.addEventListener("change", this.changeValueResponsive);
    },
    updated() {
      this.mediaQuerieList.addEventListener("change", this.changeValueResponsive);
    }
  }

</script>

<style>

  * {
    margin: 0;
    padding: 0;

    box-sizing: border-box;

    font-family: Arial, Helvetica, sans-serif;
  }

  :root {
    --white: hsl(0, 0%, 100%);
    --black: hsl(0, 0%, 0%);
    --dark-gray: hsl(0, 0%, 55%);
    --very-dark-gray: hsl(0, 0%, 41%);
  }

  @font-face {
    font-family: Alata;
    src: url(./fonts/alata/Alata-Regular.ttf);
  }

  @font-face {
    font-family: "Josefin Sans";
    src: url(./fonts/josefin-sans/static/JosefinSans-Light.ttf);
  }

  div#run {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
</style>
