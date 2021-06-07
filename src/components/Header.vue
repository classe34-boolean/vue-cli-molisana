<template>
  <header>
      <a href="/">
        <img src="../assets/images/logo.png" alt="Logo la Molisana">
      </a>
      <nav>
          <ul>
              <li v-for="(link, index) in links" :key="index">
                  <a :href="link.url" :class="{ active: link.current }">{{ link.text }}</a>
              </li>
          </ul>
      </nav>
  </header>
</template>

<script>
export default {
    name: "Header",
    data: function() {
        return {
            links: [
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
    }, 
    methods: {
        saluta: function() {
            alert("Ciao");
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "../style/variables";

    header {
        text-align: center;
    }

    ul {
        margin: 30px 0;
        display: flex;
        justify-content: center;
        list-style: none;

        li {
            a {
                padding: 15px;
                color: black;
                font-size: 18px;
                font-weight: 600;
                text-decoration: none;

                &.active,
                &:hover {
                    background-color: rgba($brandColor, 0.4);
                }
            }
        }
    }
</style>