<template>
  <div class="container">
    <div class="box-relative">
      <picture>
        <source
          srcset="../assets/home/background-home-mobile.jpg"
          media="(max-width: 576px)"
        />
        <source
          srcset="../assets/home/background-home-tablet.jpg"
          media="(min-width: 577px) and (max-width: 768px)"
        />
        <img src="../assets/home/background-home-desktop.jpg" />
      </picture>
      <span class="border"></span>
      <Nav />
      <div class="content-box">
        <span class="home-title">So, you want to travel to</span>
        <br />
        <span class="home-desc">Space</span><br />
        <span class="home-text"
          >Let’s face it; if you want to go to space, you might as well
          genuinely go to outer space and not hover kind of on the edge of it.
          Well sit back, and relax because we’ll give you a truly out of this
          world experience!</span
        >
      </div>
      <router-link to="/destination">
        <div class="btn">Explore</div>
      </router-link>
    </div>
  </div>
</template>

<script>
import Nav from "@/components/NavBar.vue";
export default {
  components: {
    Nav,
  },
};
</script>

<style scoped lang="sass">
.box-relative
  position: relative
  :deep(.home)
    border-bottom: #ffffff 3px solid
  :deep(.ham-home)
    border-right: #ffffff 4px solid
  .content-box
    position: absolute
    left: 12%
    top: 40%
    width: 35%
    font-family: 'Barlow Condensed', sans-serif
    color: #ffffff
    @include md
      position: absolute
      top: 17%
      left: 50%
      transform: translateX(-50%)
      width: 70%
      text-align: center
    @include sm
      position: absolute
      top: 15%
      left: 50%
      transform: translateX(-50%)
      width: 90%
      text-align: center
    .home-title
      font-family: 'Barlow Condensed', sans-serif
      letter-spacing: 0.295rem
      font-size: 1.75rem
      font-weight: 400
      line-height: 3.125rem
      text-transform: uppercase
      @include md
        font-size: 1.25rem
      @include sm
        font-size: 1rem
    .home-desc
      font-family: 'Bellefair', serif
      text-transform: uppercase
      font-size: 9.375rem
      @include sm
        font-size: 5rem
    .home-text
      font-family: 'Barlow', sans-serif
      font-size: 1.125rem
      font-weight: 400
      line-height: 2rem
      letter-spacing: 0.169rem
      @include md
        font-size: 1rem
        line-height: 1.75rem
      @include sm
        display: block
        margin-top: 5%
        font-size: 0.938rem
        line-height: 1.563rem
  .btn
    z-index: 2
    position: absolute
    top: 45%
    right: 12%
    background: #ffffff
    width: 274px
    height: 274px
    line-height: 274px
    border-radius: 50%
    color: #0B0D17
    font-size: 2rem
    letter-spacing: 0.125rem
    text-align: center
    text-transform: uppercase
    font-family: 'Bellefair', serif
    @include md
      width: 242px
      height: 242px
      line-height: 242px
      position: absolute
      top: 65%
      left: 50%
      transform: translateX(-50%)
    @include sm
      width: 150px
      height: 150px
      line-height: 150px
      font-size: 1.125rem
      position: absolute
      top: 60%
      left: 50%
      transform: translateX(-50%)
  .btn::before
    content: ''
    opacity: 0
    position: absolute
    top: -25%
    left: -25%
    background: #ffffff
    width: 150%
    height: 150%
    border-radius: 50%
  .btn:hover::before
    opacity: 0.1
</style>
