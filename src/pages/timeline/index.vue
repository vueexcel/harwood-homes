<template>
  <q-page class="timeline">
    <div class="header-spacer"></div>
    <div class="container-logo flex flex-center q-pt-xl">
      <img alt="Quasar logo" src="~assets/timeline-icon-big.png" />
    </div>
    <div class="container-timeline">
      <q-timeline color="brown-3">
        <div class="title text-center">Critical Path Timeline</div>

        <q-timeline-entry subtitle="Lorem ipsum dolor sit amet consectetur">
        </q-timeline-entry>
        <q-timeline-entry subtitle="Ut enim ad minim veniam, quis nostrud">
        </q-timeline-entry>
        <q-timeline-entry subtitle="Duis aute irure dolor in reprehenderit lau">
        </q-timeline-entry>
        <q-timeline-entry subtitle="Excepteur sint occaecat cupidatat lore">
        </q-timeline-entry>
        <q-timeline-entry subtitle="Laboris nisi ut aliquip ex ea commodos">
        </q-timeline-entry>
        <q-timeline-entry subtitle="Cillum dolore eu fugiat nulla pariaturus">
        </q-timeline-entry>
        <q-timeline-entry subtitle="Tellus pellentesque eu tincidunt tortor">
        </q-timeline-entry>
        <q-timeline-entry subtitle="Scelerisque purus semper eget duisis">
        </q-timeline-entry>
      </q-timeline>
    </div>
  </q-page>
</template>

<script>
export default {
  name: "Timeline",
};
</script>

<style lang="scss">
.timeline {
  background: url("../../assets/timeline-bg.png"), rgba(0, 0, 0, 0.8);
  background-size: cover;
  position: absolute;
  top: 0;
  width: 100%;
  height: 100vh;
  .header-spacer {
    margin-top: 100px;
  }
  .container-timeline {
    background: #fff;
    height: 60vh;
    width: 100%;
    overflow-y: scroll;
    position: absolute;
    bottom: 80px;
    border-radius: 20px 20px 0 0;
    padding: 0 2.25rem;
    .title {
      font-weight: bold;
      font-size: 22px;
      color: #153548;
      margin-top: 2.3125rem;
      margin-bottom: 2.3125rem;
    }
    .q-timeline__entry {
      margin-bottom: -3px;
    }
    .q-timeline__subtitle {
      text-transform: unset;
      font-size: 15px;
    }
    .q-timeline__dot:after {
      top: 18px;
    }
  }
}
</style>
