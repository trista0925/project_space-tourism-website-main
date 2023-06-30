<template>
  <div class="container">
    <div class="box-relative">
      <picture>
        <source
          srcset="../assets/technology/background-technology-mobile.jpg"
          media="(max-width: 576px)"
        />
        <source
          srcset="../assets/technology/background-technology-tablet.jpg"
          media="(min-width: 577px) and (max-width: 768px)"
        />
        <img src="../assets/technology/background-technology-desktop.jpg" />
      </picture>
      <span class="border"></span>
      <Nav />
      <div v-bind:class="active" @click.prevent class="sub-nav">
        <span
          class="tech-1"
          :class="{ dot: selected == 0 }"
          @click="makeActive('tech-1'), (selected = 0)"
          >1</span
        >
        <span
          class="tech-2"
          :class="{ dot: selected == 1 }"
          @click="makeActive('tech-2'), (selected = 1)"
          >2</span
        >
        <span
          class="tech-3"
          :class="{ dot: selected == 2 }"
          @click="makeActive('tech-3'), (selected = 2)"
          >3</span
        >
      </div>
      <div class="content-box">
        <div class="pick">
          <span style="opacity: 0.25; font-weight: 700">03</span> SPACE LAUNCH
          101
        </div>
        <div v-if="active === 'tech-1'">
          <div class="list">
            <div class="content-img">
              <picture>
                <source
                  srcset="
                    ../assets/technology/image-launch-vehicle-landscape.jpg
                  "
                  media="(max-width: 576px)"
                />
                <source
                  srcset="
                    ../assets/technology/image-launch-vehicle-landscape.jpg
                  "
                  media="(min-width: 577px) and (max-width: 768px)"
                />
                <img
                  src="../assets/technology/image-launch-vehicle-portrait.jpg"
                />
              </picture>
            </div>
            <div class="content">
              <span class="tech-sub">THE TERMINOLOGY…</span><br />
              <span class="tech-title">LAUNCH VEHICLE</span>
              <span class="tech-desc"
                >A launch vehicle or carrier rocket is a rocket-propelled
                vehicle used to carry a payload from Earth's surface to space,
                usually to Earth orbit or beyond. Our WEB-X carrier rocket is
                the most powerful in operation. Standing 150 metres tall, it's
                quite an awe-inspiring sight on the launch pad!</span
              >
            </div>
          </div>
        </div>
        <div v-if="active === 'tech-2'">
          <div class="list">
            <div class="content-img">
              <picture>
                <source
                  srcset="../assets/technology/image-spaceport-landscape.jpg"
                  media="(max-width: 576px)"
                />
                <source
                  srcset="../assets/technology/image-spaceport-landscape.jpg"
                  media="(min-width: 577px) and (max-width: 768px)"
                />
                <img src="../assets/technology/image-spaceport-portrait.jpg" />
              </picture>
            </div>
            <div class="content">
              <span class="tech-sub">THE TERMINOLOGY…</span><br />
              <span class="tech-title">SPACEPORT</span>
              <span class="tech-desc"
                >A spaceport or cosmodrome is a site for launching (or
                receiving) spacecraft, by analogy to the seaport for ships or
                airport for aircraft. Based in the famous Cape Canaveral, our
                spaceport is ideally situated to take advantage of the Earth's
                rotation for launch.</span
              >
            </div>
          </div>
        </div>
        <div v-if="active === 'tech-3'">
          <div class="list">
            <div class="content-img">
              <picture>
                <source
                  srcset="
                    ../assets/technology/image-launch-vehicle-landscape.jpg
                  "
                  media="(max-width: 576px)"
                />
                <source
                  srcset="
                    ../assets/technology/image-launch-vehicle-landscape.jpg
                  "
                  media="(min-width: 577px) and (max-width: 768px)"
                />
                <img
                  src="../assets/technology/image-space-capsule-portrait.jpg"
                />
              </picture>
            </div>
            <div class="content">
              <span class="tech-sub">THE TERMINOLOGY…</span><br />
              <span class="tech-title">SPACE CAPSULE</span>
              <span class="tech-desc"
                >A space capsule is an often-crewed spacecraft that uses a
                blunt-body reentry capsule to reenter the Earth's atmosphere
                without wings. Our capsule is where you'll spend your time
                during the flight. It includes a space gym, cinema, and plenty
                of other activities to keep you entertained.</span
              >
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
      active: "tech-1",
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
  :deep(.technology)
    border-bottom: #ffffff 3px solid
  :deep(.ham-technology)
    border-right: #ffffff 4px solid
  .sub-nav
    z-index: 2
    position: absolute
    width: 10%
    top: 40%
    left: 12%
    display: flex
    flex-direction: column
    @include md
      width: 100%
      top: 57%
      left: 0
      flex-direction: row
      justify-content: center
    @include sm
      width: 100%
      top: 42%
      left: 0
      flex-direction: row
      justify-content: center
    .tech-1,.tech-2,.tech-3
      width: 80px
      height: 80px
      border-radius: 50%
      display: flex
      cursor: pointer
      opacity: 0.2
      margin: 10% 0
      color: #FFFFFF
      font-size: 2rem
      font-family: 'Bellefair', serif
      justify-content: center
      align-items: center
      border: #FFFFFF 1px solid
      @include md
        font-size: 1.5rem
        width: 60px
        height: 60px
        margin: 0 1%
      @include sm
        font-size: 1rem
        width: 40px
        height: 40px
        margin: 0 2%
    .tech-1:hover,.tech-2:hover,.tech-3:hover
      opacity: 1
    .dot
      opacity: 1
      background: #ffffff
      color: #0B0D17
  .content-box
    position: absolute
    top: 25%
    left: 12%
    @include md
      top: 15%
      left: 0
    @include sm
      top: 14%
      left: 0
    .pick
      font-family: 'Barlow Condensed', sans-serif
      font-size: 1.75rem
      letter-spacing: 0.295rem
      text-transform: uppercase
      @include md
        margin-left: 4%
        font-size: 1.25rem
      @include sm
        text-align: center
        font-size: 1rem
    .list
      display: flex
      flex-direction: row-reverse
      justify-content: space-between
      align-items: center
      @include md
        flex-direction: column
      @include sm
        flex-direction: column
      .content-img
        width: 45%
        @include md
          width: 100%
          margin: 8%
        @include sm
          width: 100%
          margin: 10%
      .content
        width: 45%
        margin-right: 5%
        margin: 0 12% 0
        @include md
          width: 55%
          margin: 8%
          text-align: center
        @include sm
          width: 85%
          margin: 15%
          text-align: center
        .tech-sub
          font-family: 'Barlow Condensed', sans-serif
          text-transform: uppercase
          font-size: 1rem
          letter-spacing: 0.169rem
          color: #D0D6F9
          @include md
            font-size: 1rem
          @include sm
            font-size: 1rem
        .tech-title
          font-family: 'Bellefair', serif
          text-transform: uppercase
          font-size: 3.5rem
          display: block
          margin: 3% 0
          @include md
            font-size: 2.5rem
          @include sm
            font-size: 1.5rem
        .tech-desc
          font-family: 'Barlow', sans-serif
          font-size: 1.125rem
          font-weight: 400
          color: #D0D6F9
          line-height: 2rem
          @include md
            font-size: 1rem
            line-height: 1.75rem
          @include sm
            font-size: 0.938rem
            line-height: 2rem
</style>
