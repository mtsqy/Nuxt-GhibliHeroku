<template>
  <div class="container">
    <div class="content">
      <h5>Title</h5>
      <h2>{{film.title}}</h2>
      <div class="content__item">
        <h5>Producer</h5>
        <p class="content__txt">{{film.producer}}</p>
      </div>
      <div class="content__item">
        <h5>Director</h5>
        <p class="content__txt">{{film.director}}</p>
      </div>
      <div class="content__item">
        <h5>Release Date</h5>
        <p class="content__txt">{{film.release_date}}</p>
      </div>    
      <div class="content__item description">
        <h5>Description</h5>
        <p class="content__txt">{{film.description}}</p>
      </div>
    </div>
    <nuxt-link class="btn__back" to="/"></nuxt-link>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      film: [],
      id: this.$route.params.id
    };
  },
  async created() {
    const baseUrl = 'https://ghibliapi.herokuapp.com/films',
    config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const res = await axios.get(`${baseUrl}/${this.id}`, config);
      this.film = res.data;
    } catch (err) {
      console.log(err)
    }
  },
  head() {
    return {
      title: this.film.title,
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Film Page"
        }
      ]
    };
  }
}
</script>

<style lang="sass">
.container
    box-sizing: border-box
    width: 100%
    height: 100vh
    overflow-x: hidden
    padding: 2rem
.content
    box-sizing: border-box
    padding: 2rem
    width: 100%
    border-radius: 2rem
    border: 1.5px solid #f5f5f5
    box-shadow: 4px 4px 16px rgba(236, 236, 236, 0.267), 0 0 16px  rgba(245, 245, 245, 0.5)
    &__item
      margin: .6rem 0
    .description
      max-width: 560px
      overflow: hidden
.btn
  &__back
    position: absolute
    left: 2rem
    bottom: 2rem
    display: flex
    width: 3.5rem
    height: 3.5rem
    border: none
    border-radius: 50%
    color: #ffffff
    background: #FE7D3B
    box-shadow: -7px -7px 14px #FFFFFF, 5px 5px 15px #FFAC81
    &::before
      content: "Back"
      font-weight: 550
      position: absolute
      top: 50%
      left: 50%
      transform: translate(-50%,-50%)
</style>