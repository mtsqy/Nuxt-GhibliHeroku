<template>
  <div class="container">
    <h1 class="container__title">Ghibli Movies</h1>
    <div class="container__cards">
      <app-card 
      v-for="film in films" 
      :key="film.id"
      :id="film.id"
      :film="film"
      :colors="colors"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Card from "@/components/Card";

export default {
  components: {
    appCard: Card
  },
  data() {
    return {
      films: [],
    }
  },
  async created() {
    const baseUrl = 'https://ghibliapi.herokuapp.com/films';
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const res = await axios.get(`${baseUrl}`, config);
      this.films = res.data;
    } catch (err) {
      console.log(err)
    }
  },
  methods: {
    async searchInput(txt) {
      const config = {
        headers: {
          Accept: "application/json"
        }
      }
      try {
        const res = await axios.get(`${baseUrl}`, config);
        this.films = res.data;
      } catch (err) {
        console.log(err)
      }
    }
  },
  head() {
    return {
      title: "Ghibli Movies",
      meta: [
        {
          hid: "desc",
          name: "desc",
          content: "test"
        }
      ]
    };
  }
};
</script>

<style lang="sass">
  .container
    width: 100%
    height: 100vh
    overflow-x: hidden
    padding: 2rem
    &__title
      color: 
    &__cards
      position: relative
      display: flex
      flex-wrap: wrap
      flex-direction: row
      width: 100%
</style>
