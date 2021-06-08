<template>
    <footer>
      <div class="container cols">
          <div>
              <a href="/">
                <img src="../assets/images/logo.png" alt="Logo la Molisana">
            </a>
          </div>
          <div>
              <h3>Pastificio</h3>
              <nav>
                    <ul>
                        <li><a href="#">Il Pastificio</a></li>
                        <li><a href="#">Grano</a></li>
                        <li><a href="#">Filiera</a></li>
                        <li><a href="#">100 anni di pasta</a></li>
                        <li><a href="#">Sartoria della pasta</a></li>
                    </ul>
                </nav>
          </div>
          <div>
              <h3>Prodotti</h3>
              <nav>
                  <ul>
                      <li 
                        v-for="(anchor, index) in anchors" 
                        :key="index">
                        <a :href="anchor.url">{{ anchor.text }}</a>
                    </li>
                      <!-- <li><a href="#">Le classiche</a></li>
                        <li><a href="#">Le Integrali</a></li>
                        <li><a href="#">Le Speciali</a></li>
                        <li><a href="#">Le Biologiche</a></li>
                        <li><a href="#">Le Gluten-free</a></li> -->
                  </ul>
              </nav>
          </div>
      </div>
    </footer>
</template>

<script>
export default {
    name: "Footer",
    // Props, sintassi ad array
    // props: ["anchors"]

    // Props, sintassi ad oggetti
    props: {
        anchors: {
            type: Array,
            required: true
        }
    }
}
</script>

<style lang="scss" scoped>
    @import "../style/variables";
    @import "../style/mixins";

    footer {
        padding-bottom: 150px;
        background: url('../assets/images/footer.jpg') no-repeat left bottom;
        // @include full-backgroundsize-cover;
        @include full-backgroundsize(100% auto);
    }
    .cols {
        
        img {
           width: 70%; 
        }

        & > div {
            float: left;
            width: calc(100% / 3);
        }

        &::after {
            @include clearfix;
        }
    }

    ul {
        list-style: none;

        li {
            a {
                display: block;
                padding: 2px 0;
                text-decoration: none;
                color: $brandColor;

                &:hover {
                    text-decoration: underline;
                }
            }
        }
    }

    h3 {
        margin-bottom: 10px;
        text-transform: uppercase;
        color: $brandColor;
        font-size: 24px;
    }
</style>