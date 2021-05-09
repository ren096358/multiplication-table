<template>
  <div id="app">
    <MultiplicationTable />
    <div class="footer">{{ footer.text }}</div>
  </div>
</template>

<script>
import MultiplicationTable from './components/MultiplicationTable.vue'

export default {
  name: 'App',
  components: {
    MultiplicationTable,
  },
  data() {
    return {
      footer: {
        text: 'Copyright © 2019 HexSchool. All rights reserved.',
      },
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 1280px;
  height: 100%;
  font-family: PingFang TC, Helvetica Neue, Microsoft JhengHei;
  color: #2eb738;
}
.footer {
  background-color: #2eb738;
  color: #f0f0f0;
  padding: 8px 85px 8px 0;
  text-align: right;
}
</style>
