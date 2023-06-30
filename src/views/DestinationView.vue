<template>
  <div class="container">
    <div class="box-relative">
      <picture>
        <source
          srcset="../assets/destination/background-destination-mobile.jpg"
          media="(max-width: 576px)"
        />
        <source
          srcset="../assets/destination/background-destination-tablet.jpg"
          media="(min-width: 577px) and (max-width: 768px)"
        />
        <img src="../assets/destination/background-destination-desktop.jpg" />
      </picture>
      <span class="border"></span>
      <Nav />
      <div v-bind:class="active" @click.prevent class="sub-nav">
        <span class="moon" @click="makeActive('moon')">MOON</span>
        <span class="mars" @click="makeActive('mars')">MARS</span>
        <span class="europa" @click="makeActive('europa')">EUROPA</span>
        <span class="titan" @click="makeActive('titan')">TITAN</span>
      </div>
      <div class="content-box">
        <div class="pick">
          <span style="opacity: 0.25; font-weight: 700">01</span> Pick your
          destination
        </div>
        <div v-if="active === 'moon'">
          <div class="list">
            <div class="content-img">
              <img src="../assets/destination/image-moon.png" alt="" />
            </div>
            <div class="content">
              <span class="des-title">MOON</span><br />
              <span class="des-desc"
                >See our planet as you’ve never seen it before. A perfect
                relaxing trip away to help regain perspective and come back
                refreshed. While you’re there, take in some history by visiting
                the Luna 2 and Apollo 11 landing sites.</span
              >
              <hr />
              <div class="des-container">
                <div class="des-item">
                  <p class="des-box-title">AVG. DISTANCE</p>
                  <p class="des-box-text">384,400 KM</p>
                </div>
                <div class="des-item">
                  <p class="des-box-title">EST. TRAVEL TIME</p>
                  <p class="des-box-text">3 DAYS</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-if="active === 'mars'">
          <div class="list">
            <div class="content-img">
              <img src="../assets/destination/image-mars.png" alt="" />
            </div>
            <div class="content">
              <span class="des-title">MARS</span><br />
              <span class="des-desc"
                >Don’t forget to pack your hiking boots. You’ll need them to
                tackle Olympus Mons, the tallest planetary mountain in our solar
                system. It’s two and a half times the size of Everest!</span
              >
              <hr />
              <div class="des-container">
                <div class="des-item">
                  <p class="des-box-title">AVG. DISTANCE</p>
                  <p class="des-box-text">225 MIL. KM</p>
                </div>
                <div class="des-item">
                  <p class="des-box-title">EST. TRAVEL TIME</p>
                  <p class="des-box-text">9 MONTHS</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-if="active === 'europa'">
          <div class="list">
            <div class="content-img">
              <img src="../assets/destination/image-europa.png" alt="" />
            </div>
            <div class="content">
              <span class="des-title">EUROPA</span><br />
              <span class="des-desc"
                >The smallest of the four Galilean moons orbiting Jupiter,
                Europa is a winter lover’s dream. With an icy surface, it’s
                perfect for a bit of ice skating, curling, hockey, or simple
                relaxation in your snug wintery cabin.</span
              >
              <hr />
              <div class="des-container">
                <div class="des-item">
                  <p class="des-box-title">AVG. DISTANCE</p>
                  <p class="des-box-text">628 MIL. KM</p>
                </div>
                <div class="des-item">
                  <p class="des-box-title">EST. TRAVEL TIME</p>
                  <p class="des-box-text">3 YEARS</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-if="active === 'titan'">
          <div class="list">
            <div class="content-img">
              <img src="../assets/destination/image-titan.png" alt="" />
            </div>
            <div class="content">
              <span class="des-title">TITAN</span><br />
              <span class="des-desc"
                >The only moon known to have a dense atmosphere other than
                Earth, Titan is a home away from home (just a few hundred
                degrees colder!). As a bonus, you get striking views of the
                Rings of Saturn.</span
              >
              <hr />
              <div class="des-container">
                <div class="des-item">
                  <p class="des-box-title">AVG. DISTANCE</p>
                  <p class="des-box-text">1.6 BIL. KM</p>
                </div>
                <div class="des-item">
                  <p class="des-box-title">EST. TRAVEL TIME</p>
                  <p class="des-box-text">7 YEARS</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Nav from "@/components/NavBar.vue";

export default {
  components: {
    Nav,
  },
  data() {
    return {
      active: "moon",
    };
  },

  methods: {
    makeActive: function (item) {
      this.active = item;
    },
  },
};
</script>

<style scoped lang="sass">
.box-relative
  position: relative
  :deep(.destination)
    border-bottom: #ffffff 3px solid
  :deep(.ham-destination)
    border-right: #ffffff 4px solid
  .sub-nav
    z-index: 2
    position: absolute
    top: 28%
    left: 57%
    display: flex
    letter-spacing: 0.169rem
    font-family: 'Barlow Condensed', sans-serif
    cursor: pointer
    @include md
      width: 100%
      top: 56%
      left: 0
      justify-content: center
    @include sm
      width: 100%
      top: 38%
      left: 0
      justify-content: center
    .moon,.mars,.europa,.titan
      margin: 8%
      padding: 3% 0
      @include md
        margin: 0 3%
        padding: 1% 0
      @include sm
        font-size: 0.875rem
        margin: 0 2%
        padding: 2% 0
    .moon:hover,.mars:hover,.europa:hover,.titan:hover
      color: #D0D6F9
      border-bottom: #ffffff 3px solid
      opacity: 0.5
  .mars>.mars,.moon>.moon,.europa>.europa,.titan>.titan
    border-bottom: #ffffff 3px solid
  .content-box
    position: absolute
    left: 12%
    top: 23%
    @include md
      top: 14%
      left: 0
    @include sm
      top: 11%
      left: 0
      text-align: center
    .pick
      font-family: 'Barlow Condensed', sans-serif
      font-size: 1.75rem
      letter-spacing: 0.295rem
      text-transform: uppercase
      @include md
        margin-left: 4%
        font-size: 1.25rem
        letter-spacing: 0.211rem
      @include sm
        font-size: 1rem
        letter-spacing: 0.169rem
    .list
      display: flex
      flex-direction: row
      justify-content: start
      align-items: center
      margin-top: 5%
      @include md
        margin-top: 0
        flex-direction: column
      @include sm
        margin-top: 0
        flex-direction: column
      .content-img
        margin: 0 12% 0 5%
        width: 35%
        @include md
          width: 45%
          margin: 5% 0 7%
        @include sm
          width: 45%
          margin: 7% 0 20%
      .content
        width: 35%
        @include md
          width: 70%
          text-align: center
          margin: 5% 0
        @include sm
          width: 75%
          text-align: center
        .des-title
          font-family: 'Bellefair', serif
          text-transform: uppercase
          font-size: 6.25rem
          @include md
            font-size: 5rem
          @include sm
            font-size: 3.5rem
        .des-desc
          font-family: 'Barlow', sans-serif
          font-size: 1.125rem
          font-weight: 400
          line-height: 2rem
          @include md
            font-size: 1rem
            line-height: 1.75rem
          @include sm
            display: block
            font-size: 1rem
            line-height: 1.8rem
        hr
          margin: 10% 0
          border: #383B4B 1px solid
          @include md
            width: 100%
            margin: 7% 0
          @include sm
            width: 100%
            margin: 10% 0
        .des-container
          display: flex
          width: 100%
          @include sm
            flex-direction: column
          .des-item
            flex: auto
            @include sm
              margin: 0 0 10%
            .des-box-title
              font-family: 'Barlow Condensed', sans-serif
              font-size: 0.875rem
              font-weight: 400
              margin-bottom: 5%
              letter-spacing: 0.148rem
              color: #D0D6F9
            .des-box-text
              font-family: 'Bellefair', serif
              font-size: 1.75rem
              font-weight: 400
</style>
