<template>
  <div id="app">
    <div class="frame-external">
      <div class="frame-internal">
        <header>
          <app-header></app-header>
        </header>
        <!-- <main><app-slider></app-slider></main> -->
        <footer>
          <app-footer></app-footer>
        </footer>


      </div>
    </div>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Footer from './components/Footer.vue';
  // import Slider from './components/Slider.vue';
  export default {
    name: 'App',
    components: {
      'app-header': Header,
      'app-footer': Footer,
      // 'app-slider': Slider,
    }
  }
</script>

<style lang="scss">
  :root {
    --white-color: #fff;
  }


  @font-face {
    font-family: "Gilroy-Regular";
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: local("Gilroy-Regular"),
      url("./fonts/Gilroy-Regular.woff2") format("woff2"),
      url("./fonts/Gilroy-Regular.woff") format("woff");
  }

  @font-face {
    font-family: "Gilroy-Medium";
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: local("Gilroy-Medium"),
      url("./fonts/Gilroy-Medium.woff2") format("woff2"),
      url("./fonts/Gilroy-Medium.woff") format("woff");
  }

  @font-face {
    font-family: "Gilroy-Bold";
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: local("Gilroy-Bold"),
      url("./fonts/Gilroy-Bold.woff2") format("woff2"),
      url("./fonts/Gilroy-Bold.woff") format("woff");
  }

  $frame_color: #e8c07c;
  $icon_color: #ffcc00;
  $color_white: #fff;

  $font-style: Gilroy-Regular,
  Avenir,
  Helvetica,
  Arial,
  sans-serif;
  $font-medium-style: Gilroy-Medium,
  Avenir,
  Helvetica,
  Arial,
  sans-serif;
  $font-bold-style: Gilroy-Bold,
  Avenir,
  Helvetica,
  Arial,
  sans-serif;

  a,
  p,
  h1,
  h2,
  h3,
  h4,
  h5,
  h6,
  input,
  textarea,
  span {
    font-family: $font-style;
  }



  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    padding: 15px;
  }

  .frame-external {
    outline: solid 6px $frame_color;
    padding: 8px;
  }

  .frame-internal {
    outline: solid 3px $frame_color;
  }

  @media all and (max-width: 760px) {

    .frame-external,
    .frame-internal {
      outline: none;
      padding: 0px;
    }

    #app {
      padding: 0px;
    }
  }

  .contact__link a,
  .contact__link p,
  .navbar-link a {
    font-family: $font-medium-style;
  }

  .footer__headline-contact_condition {
    font-family: $font-bold-style;
    text-transform: uppercase;
    font-size: 16px;
  }

  .userSVG_fill,
  .likeSVG,
  .trashSVG {
    fill: $icon_color;
    transition: 0.2s;
  }

  .navbar__linkSVG:hover path {
    fill: $color_white;
    transition: 0.2s;
  }
</style>