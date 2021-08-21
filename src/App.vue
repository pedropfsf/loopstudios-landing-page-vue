<template>
  <div>
    <Background>
      <Header/>
      <MessageText>
        IMMERSIVE EXPERIENCES THAT DELIVER
      </MessageText>
    </Background>
    <main id="main">
      <section id="sectionFacts">
        <img
          id="imageFacts"
          src="./assets/desktop/image-interactive.jpg"
          alt="image interactive"
        />
        <article id="articleFacts">
          <div id="messageFacts">
            <h1 id="title">
              THE LEADER IN INTERACTIVE VR
            </h1>
            <p id="paragraph">
              Founded in 2011, Loopstudios has been producing world-class
              virtual reality projects for some of the best companies around
              the globe. Our award-winning creations have transformed<br> businesses
              through digital experiences that bind to their brand.
            </p>
          </div>
        </article>
      </section>
    </main>
  </div>
</template>

<script>
  import Background from './components/Background/Background.vue';
  import Header from './components/Header/Header.vue';
  import MessageText from './components/MessageText/MessageText.vue';

  export default {
    name: 'App',
    components: {
      Background,
      Header,
      MessageText
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

  main#main {
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
  }

  main#main,
  section#sectionFacts
  {
    display: flex;
  }

  section#sectionFacts {
    margin-top: 7rem;

    width: 80%;
    height: 30rem;

    position: relative;
  }
  
  img#imageFacts {
    width: 45rem;
  }

  div#messageFacts {
    background-color: var(--white);

    width: 36rem;

    padding-left: 5rem;
    padding-top: 5rem;

    position: absolute;
    right: 0;
    bottom: 0;
  }

  h1#title {
    font-family: "Josefin Sans", Helvetica, sans-serif;
    font-size: 3rem;
    font-weight: normal;

    margin-bottom: 2rem;
  }

  p#paragraph {
    color: var(--very-dark-gray);

    font-family: Atala, Helvetica, sans-serif;
    font-weight: bold;
    font-size: 15px;

    line-height: 1.7rem;
  }
</style>
