<template>
  <div id="app">
    <!-- testata della pagina -->
    <Header :links="menu" />

    <!-- /testata della pagina -->

    <!-- corpo della pagina -->
    <main>
      <Products />
    </main>
    <!-- /corpo della pagina -->

    <!-- chiusura della pagina -->
    <Footer :anchors="menu" />
    <!-- /chiusura della pagina -->
  </div>
</template>

<script>
import Header from './components/Header';
import Products from './components/Products';
import Footer from './components/Footer';

export default {
  name: 'App',
  components: {
    Header,
    Products,
    Footer
  },
  data: function() {
    return {
      menu: [
                {
                    text: "Home",
                    url: "#home",
                    current: false
                },
                {
                    text: "Prodotti",
                    url: "#prodotti",
                    current: false
                },
                {
                    text: "Chi Siamo",
                    url: "#chi-siamo",
                    current: true
                },
                {
                    text: "Contatti",
                    url: "#contatti",
                    current: false
                }
            ]
    }
  }
}
</script>

<style lang="scss">
@import "./style/general.scss";
</style>
