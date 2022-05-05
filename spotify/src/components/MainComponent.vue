<template>
  <main id="site_main">
    <div class="container">
      <div class="row">
        <div class="col" :key="index" v-for="(disco, index) in dischi">
          <div class="card">
            <div class="image">
              <img :src="disco.poster" alt="" />
            </div>
            <div class="text">
              <h2>{{ disco.title }}</h2>
              <div class="autore">
                <div class="nome">{{ disco.author }}</div>
                <div class="anno">{{ disco.year }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";

export default {
  name: "MainComponent",

  data() {
    return {
      dischi: "",
    };
  },

  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((oggetto) => {
        this.dischi = oggetto.data.response;
      });
  },
};
</script>

<style lang='scss'>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

#site_main {
    background-color: #1E2D3B;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    text-align: center;
    padding-top: 80px;
    padding-bottom: 80px;
    height: calc(100vh - 70px);
    overflow: auto;
    

    
    

  .container {
      width: 1200px;
      margin: auto;

      

    .row {
      display: flex;
      flex-wrap: wrap;
      column-gap: 40px;
      row-gap: 20px;
      
      

      .col {
        width: calc(100% / 5 - 40px + 40px/5);

        .card {
            background-color: #2E3A46;
            padding: 20px;
            height: 100%;

          .image {
            img {
              width: 100%;
              aspect-ratio: 1/1;
              object-fit: cover;
            }
          }

          .text {
            h2 {
                text-transform: uppercase;
                color: white;
                padding-bottom: 1rem;
            }

            .autore {
                text-transform: capitalize;
                color: #808078;
                font-size: 1.2rem;
            }
          }
        }
      }
    }
  }
}
</style>