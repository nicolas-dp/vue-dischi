<template>
  <section class="main_grid" v-if="!loading">
    <select class="form-select" aria-label="Default select example" >
      <option selected>Open this select menu</option>
      <option>Pop</option>
      <option>Jazz</option>
      <option>Metal</option>
      <option>Rock</option>
    </select>

    <div class="container">
      <div class="row row-cols-1 row-cols-sm-2 row-cols-md-5 p-5">
        <div class="col card bg_color_dark_side p-3 m-3" v-for="(card, index) in cards" :key="index" style="width: 12rem">
          <img class="card-img-top img-fluid" :src="card.poster" :alt="card.title"/>
          <div class="card-body text-center d-flex flex-column">
            <h5 class="card-title text-white">{{ card.title }}</h5>
            <small class="card-text text-secondary">
              {{ card.author }}
            </small>
            <small class="card-text text-secondary">
              {{ card.year }}
            </small>
          </div>
        </div>
      </div>
    </div>
  </section>
  <div
    class="d-flex min-vh-100 align-items-center justify-content-center"
    v-else
  >
    <img height="70" src="http://www.itismajo.it/Immagini/Icon/caricamento.gif" alt="">
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "SiteMain",
  data() {
    return {
      API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
      cards: null,
      loading: true,
      error: null,
    };
  },
  methods: {
    callApi() {
      axios
        .get(this.API_URL)
        .then((response) => {
          //console.log(response);
          //console.log(this.cards);
          this.cards = response.data.response;
          /* this.card = response.data.response;*/
          this.loading = false;
          //console.log(this.cards);
        })

        .catch((error) => {
          console.log(error);
          this.error = `Sorry There is a problem! ${error.message}`;
        });
    },

    filterGenr(){
      console.log(this.$options); 
    }
  },

  mounted() {
    this.callApi();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
</style>