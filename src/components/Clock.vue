<template>
  <div class="container">
    <img
      class="clock"
      src="https://ren096358.github.io/js-underground/clock/image/clock-bg.png"
    />
    <img
      id="hour"
      class="hand hour"
      src="https://ren096358.github.io/js-underground/clock/image/hour-hand.png"
      :style="{
        transform: 'translate(0, -50%) rotate(' + degree.hour + 'deg)',
      }"
    />
    <img
      id="minute"
      class="hand minute"
      src="https://ren096358.github.io/js-underground/clock/image/minute-hand.png"
      :style="{
        transform: 'translate(-50%, -100%) rotate(' + degree.minute + 'deg)',
      }"
    />
    <img
      id="second"
      class="hand second"
      src="https://ren096358.github.io/js-underground/clock/image/second-hand.png"
      :style="{
        transform: 'translate(-50%, 0) rotate(' + degree.second + 'deg)',
      }"
    />
  </div>
</template>

<script>
export default {
  name: 'Clock',
  data() {
    return {
      degree: {
        hour: null,
        minute: null,
        second: null,
      },
    }
  },
  mounted() {
    let vm = this
    setInterval(function () {
      vm.clock()
    }, 1000)
  },
  methods: {
    clock() {
      let d = new Date()
      let hour = d.getHours()
      let min = d.getMinutes()
      let sec = d.getSeconds()

      this.degree.second = (sec * 360) / 60 + 180
      this.degree.minute = (min * 360) / 60 + (6 * sec) / 60
      this.degree.hour = (hour * 360) / 12 + (30 * min) / 60 - 90
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
  margin: 0px;
}

body {
  background-color: #293b29;
}

.clock {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.hand {
  position: absolute;
  top: 50%;
  left: 50%;
}

.hour {
  z-index: 3;
  transform-origin: 0 50%;
  transform: translate(0, -50%) rotate(-90deg);
}

.minute {
  z-index: 2;
  transform-origin: 50% 100%;
  transform: translate(-50%, -100%);
}

.second {
  z-index: 1;
  transform-origin: 50% 0;
  transform: translate(-50%, 0) rotate(180deg);
}
</style>
