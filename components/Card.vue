<template>
  <div class="card">
    <div class="card__item">
      <div class="card__item__title">
        <h2>{{film.title}}</h2>
        <span class="card__item__title__separator"></span>
      </div>
      <div class="card__item__rating">
        <span style="margin: 0 .2rem;">{{glyph}}</span>
        <h5 style='color: #ffffff;'>{{film.rt_score}}</h5>
      </div>
      <div class="card__item__desc">
        <p>{{film.description}}</p>
      </div>
      <div class="card__item__bottom">
        <nuxt-link class="card__item__bottom__btn" :to="'./'+id"></nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>

export default {
    name: "Card",
    props: ["film", "id"],
    data() {
      return {
        glyph: '\u2729'
      };
  },
}
</script>

<style lang="sass" scooped>
  .card
    box-sizing: border-box
    flex: 0 0 240px
    overflow: hidden
    text-decoration: none
    &__item
      box-sizing: border-box
      margin: .3rem
      padding: 1.2rem
      border-radius: 1rem
      height: 320px
      display: flex
      flex-direction: column
      justify-content: space-between
      border: 1.5px solid #f5f5f5
      box-shadow: 4px 4px 16px rgba(236, 236, 236, 0.267), 0 0 16px  rgba(245, 245, 245, 0.5)
      &__title
        display: flex
        flex-direction: column
        &__separator
          margin: 1rem 0
          height: 2.4px
          width: 100%
          background-color: #42ffff
          background-image: linear-gradient(49deg, #42ffff 0%, #f9ccff 69%)
          border-radius: 1rem
      &__rating
        position: relative
        display: flex
        align-items: center
        justify-content: center
        padding-right: 0.3rem
        width: 3.2rem
        height: 1.6rem
        border: none
        border-radius: 1rem
        color: #ffffff
        background: #feea3b
        box-shadow: -7px -7px 14px #FFFFFF, 3px 4px 15px -1px #fcf26f
        p
      &__desc
        overflow: hidden
        margin: 1.4rem 0
        height: 46px
      &__bottom
        display: flex
        flex-direction: row
        justify-content: flex-end
        align-items: flex-end
        &__btn
          position: relative
          display: flex
          width: 2.25rem
          height: 2.25rem
          border: none
          border-radius: 50%
          color: #ffffff
          background: #9B5DE5
          box-shadow: -7px -7px 14px #FFFFFF, 4px 4px 15px #b78ceb
          &::before
            content: "\00bb"
            font-weight: 550
            position: absolute
            top: 50%
            left: 50%
            transform: translate(-50%,-55%)
</style>