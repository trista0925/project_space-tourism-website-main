<template>
  <div class="container">
    <div class="box-relative">
      <picture>
        <source
          srcset="../assets/crew/background-crew-mobile.jpg"
          media="(max-width: 576px)"
        />
        <source
          srcset="../assets/crew/background-crew-tablet.jpg"
          media="(min-width: 577px) and (max-width: 768px)"
        />
        <img src="../assets/crew/background-crew-desktop.jpg" />
      </picture>
      <span class="border"></span>
      <Nav />
      <div v-bind:class="active" @click.prevent class="sub-nav">
        <span
          class="crew-1"
          :class="{ dot: selected == 0 }"
          @click="makeActive('crew-1'), (selected = 0)"
        ></span>
        <span
          class="crew-2"
          :class="{ dot: selected == 1 }"
          @click="makeActive('crew-2'), (selected = 1)"
        ></span>
        <span
          class="crew-3"
          :class="{ dot: selected == 2 }"
          @click="makeActive('crew-3'), (selected = 2)"
        ></span>
        <span
          class="crew-4"
          :class="{ dot: selected == 3 }"
          @click="makeActive('crew-4'), (selected = 3)"
        ></span>
      </div>
      <div class="content-box">
        <div class="pick">
          <span style="opacity: 0.25; font-weight: 700">02</span> Meet your crew
        </div>
        <div v-if="active === 'crew-1'">
          <div class="list">
            <div class="content-img">
              <img src="../assets/crew/image-douglas-hurley.png" alt="" />
            </div>
            <div class="content">
              <span class="crew-sub">COMMANDER</span><br />
              <span class="crew-title">DOUGLAS HURLEY</span>
              <span class="crew-desc"
                >Douglas Gerald Hurley is an American engineer, former Marine
                Corps pilot and former NASA astronaut. He launched into space
                for the third time as commander of Crew Dragon Demo-2.</span
              >
            </div>
          </div>
        </div>
        <div v-if="active === 'crew-2'">
          <div class="list">
            <div class="content-img">
              <img src="../assets/crew/image-mark-shuttleworth.png" alt="" />
            </div>
            <div class="content">
              <span class="crew-sub">MISSION SPECIALIST</span><br />
              <span class="crew-title">MARK SHUTTLEWORTH</span>
              <span class="crew-desc"
                >Mark Richard Shuttleworth is the founder and CEO of Canonical,
                the company behind the Linux-based Ubuntu operating system.
                Shuttleworth became the first South African to travel to space
                as a space tourist.</span
              >
            </div>
          </div>
        </div>
        <div v-if="active === 'crew-3'">
          <div class="list">
            <div class="content-img">
              <img src="../assets/crew/image-victor-glover.png" alt="" />
            </div>
            <div class="content">
              <span class="crew-sub">PILOT</span><br />
              <span class="crew-title">VICTOR GLOVER</span>
              <span class="crew-desc"
                >Pilot on the first operational flight of the SpaceX Crew Dragon
                to the International Space Station. Glover is a commander in the
                U.S. Navy where he pilots an F/A-18.He was a crew member of
                Expedition 64, and served as a station systems flight engineer.
              </span>
            </div>
          </div>
        </div>
        <div v-if="active === 'crew-4'">
          <div class="list">
            <div class="content-img">
              <img src="../assets/crew/image-anousheh-ansari.png" alt="" />
            </div>
            <div class="content">
              <span class="crew-sub">FLIGHT ENGINEER</span><br />
              <span class="crew-title">ANOUSHEH ANSARI</span>
              <span class="crew-desc"
                >Anousheh Ansari is an Iranian American engineer and co-founder
                of Prodea Systems. Ansari was the fourth self-funded space
                tourist, the first self-funded woman to fly to the ISS, and the
                first Iranian in space.
              </span>
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
      active: "crew-1",
      selected: 0,
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
  :deep(.crew)
    border-bottom: #ffffff 3px solid
  :deep(.ham-crew)
    border-right: #ffffff 4px solid
  .sub-nav
    z-index: 2
    position: absolute
    width: 20%
    top: 80%
    left: 12%
    display: flex
    flex-direction: row
    @include md
      width: 100%
      top: 44%
      left: 0
      justify-content: center
    @include sm
      width: 100%
      top: 49%
      left: 0
      justify-content: center
    .crew-1,.crew-2,.crew-3,.crew-4
      width: 15px
      height: 15px
      border-radius: 50%
      background-color: #ffffff
      display: inline-block
      cursor: pointer
      opacity: 0.2
      margin-right: 10%
      @include md
        width: 10px
        height: 10px
        margin: 0 1%
      @include sm
        width: 10px
        height: 10px
        margin: 0 2%
    .crew-1:hover,.crew-2:hover,.crew-3:hover,.crew-4:hover
      opacity: 0.5
    .dot
      opacity: 1
  .content-box
    position: absolute
    bottom: 0
    left: 12%
    @include md
      left: 0
      top: 15%
    @include sm
      top: 13%
      left: 0
    .pick
      font-family: 'Barlow Condensed', sans-serif
      font-size: 1.75rem
      letter-spacing: 0.295rem
      text-transform: uppercase
      position: absolute
      top: 9%
      @include md
        position: relative
        top: 0
        font-size: 1.25rem
        margin-left: 4%
      @include sm
        position: relative
        top: 0
        text-align: center
        font-size: 1rem
    .list
      display: flex
      flex-direction: row-reverse
      justify-content: start
      align-items: center
      @include md
        flex-direction: column-reverse
      @include sm
        flex-direction: column
      .content-img
        width: 45%
        margin-left: 5%
        @include md
          position: absolute
          width: 55%
          bottom: 0
        @include sm
          position: absolute
          width: 45%
          margin: 10% 0 20%
      .content-img::after
        @include sm
          content: ''
          display: block
          width: 100%
          border-bottom: #383B4B 2px solid
      .content
        width: 45%
        @include md
          width: 60%
          text-align: center
          margin: 5% 0
        @include sm
          width: 80%
          text-align: center
          margin: 87% 0
        .crew-sub
          font-family: 'Bellefair', serif
          text-transform: uppercase
          font-size: 2rem
          opacity: 0.5
          @include md
            font-size: 1.5rem
          @include sm
            font-size: 1rem
        .crew-title
          font-family: 'Bellefair', serif
          text-transform: uppercase
          font-size: 3.5rem
          display: block
          margin: 2% 0
          @include md
            font-size: 2.5rem
          @include sm
            font-size: 1.5rem
        .crew-desc
          font-family: 'Barlow', sans-serif
          font-size: 1.125rem
          font-weight: 400
          line-height: 2rem
          color: #D0D6F9
          @include md
            font-size: 1rem
            line-height: 1.75rem
          @include sm
            font-size: 0.938rem
</style>
