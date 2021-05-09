<template>
  <div class="flex-container">
    <article>
      <div class="line line-top"></div>
      <div class="title">{{ article.title }}</div>
      <div class="subtitle">{{ article.subtitle }}</div>
      <div class="line line-bottom"></div>
      <div class="x lt">x</div>
      <div class="x lb">x</div>
      <div class="x rt">x</div>
      <div class="x rb">x</div>
    </article>
    <div class="card" v-for="amount in bord.amount" :key="amount">
      <div class="title">{{ amount + 1 }}</div>
      <div class="caculate" v-for="number in 9" :key="number">
        {{ amount + 1 }} x {{ number }} = {{ (amount + 1) * number }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Clock',
  data() {
    return {
      bord: {
        amount: 8,
      },
      article: {
        title: '九九乘法表',
        subtitle: 'MULTIPLICATION CHART',
      },
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
  margin: 0px;
}

.flex-container {
  background-color: #f0f0f0;
  padding: 60px 70px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: flex-start;
}

article {
  display: flex;
  width: 350px;
  height: 366px;
  margin: 20px 15px;
  position: relative;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

article .line {
  position: absolute;
  width: 280px;
  border-top: 1px solid #2eb738;
}

article .line-top {
  top: 15.5px;
}

article .line-bottom {
  bottom: 11.5px;
}

article .title {
  font-weight: 500;
  font-size: 56px;
}

article .subtitle {
  font-size: 24px;
}

article .x {
  position: absolute;
  font-size: 24px;
}

article .lt {
  left: 0;
  top: 0;
}

article .lb {
  left: 0;
  bottom: 0;
}

article .rt {
  right: 0;
  top: 0;
}

article .rb {
  right: 0;
  bottom: 0;
}

.card {
  background-color: #ffffff;
  width: 350px;
  height: 366px;
  margin: 20px 15px;
  padding: 50px 25px;
  border-radius: 100px 0px 30px 0px;
  box-shadow: 0px 3px 10px #d8d8d8;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: stretch;
}

.card .title {
  font-size: 128px;
  line-height: 120px;
  font-weight: bold;
  text-shadow: 4px 3px #f0f0f0;
  text-align: center;
  padding-top: 0px;
  width: auto;
}

.card .caculate {
  font-size: 24px;
  line-height: 24px;
  padding: 8px 15px;
  width: auto;
}
</style>
