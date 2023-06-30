<template>
  <div>
    <router-link to="/">
      <img src="../assets/shared/logo.svg" class="logo" alt="" />
    </router-link>
    <nav>
      <ul class="home">
        <router-link to="/">
          <li><span class="no">00</span> Home</li>
        </router-link>
      </ul>
      <ul class="destination">
        <router-link to="/destination">
          <li><span class="no">01</span> Destination</li>
        </router-link>
      </ul>
      <ul class="crew">
        <router-link to="/crew">
          <li><span class="no">02</span> Crew</li>
        </router-link>
      </ul>
      <ul class="technology">
        <router-link to="/technology">
          <li><span class="no">03</span> Technology</li>
        </router-link>
      </ul>
    </nav>
    <div class="hamburger">
      <div @click="show = !show">
        <div v-if="show">
          <img
            src="../assets/shared/icon-close.svg"
            class="close-icon"
            alt=""
          />
        </div>
        <div v-else>
          <img
            src="../assets/shared/icon-hamburger.svg"
            class="open-icon"
            alt=""
          />
        </div>
      </div>
      <Transition>
        <div class="hamburger-bg" v-show="show">
          <div class="hamburger-item">
            <router-link to="/">
              <p class="ham-home"><b>00</b> HOME</p>
            </router-link>
            <router-link to="/destination">
              <p class="ham-destination"><b>01</b> DESTINATION</p>
            </router-link>
            <router-link to="/crew">
              <p class="ham-crew"><b>02</b> CREW</p>
            </router-link>
            <router-link to="/technology">
              <p class="ham-technology"><b>03</b> TECHNOLOGY</p>
            </router-link>
          </div>
        </div>
      </Transition>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      show: false,
    };
  },
};
</script>

<style scoped lang="sass">
.box-relative
  position: relative
  .logo
    z-index: 2
  .v-enter-active,
  .v-leave-active
    transform: translate(250px, 0)
  .v-enter-from,
  .v-leave-to
    opacity: 0
  .v-enter-to,
  .v-leave-from
    opacity: 1
  .hamburger
    display: none
    @include sm
      display: block
      width: 100%
      height: 100%
      position: absolute
      top: 0
      right: 0
    .open-icon,.close-icon
      z-index: 4
      width: 20px
      height: 20px
      position: absolute
      top: 4%
      right: 5%
      cursor: pointer
    .hamburger-bg
      z-index: 3
      background: rgba(255, 255, 255, 0.04)
      backdrop-filter: blur(40.7742px)
      width: 250px
      height: 100%
      position: absolute
      top: 0
      right: 0
      transition: all 0.5s ease
      .hamburger-item
        margin: 60% 0 50% 15%
        p
          font-family: 'Barlow Condensed', sans-serif
          font-size: 1rem
          letter-spacing: 0.169rem
          padding: 3% 0
          margin: 15% 0
  nav
    display: flex
    justify-content: center
    align-items: center
    position: absolute
    width: 58%
    height: 10%
    right: 0
    top: 5%
    background: rgba(255, 255, 255, 0.04)
    backdrop-filter: blur(40.7742px)
    font-size: 0.875rem
    text-transform: uppercase
    letter-spacing: 0.169rem
    font-family: 'Barlow Condensed', sans-serif
    @include md
      backdrop-filter: none
      top: 0
    @include sm
      display: none
    ul
      margin: 5%
      padding: 4% 0
      .no
        font-weight: 700
        @include md
          display: none
    ul:hover
      position: relative
      border-bottom: rgba(255, 255, 255, .5) 3px solid
</style>
