<template>
  <div id="app" v-html="code"></div>
</template>

<script>
import Code from './components/Code.vue';
import codes from './datas/codes.js';
import colors from './datas/colors.js';

export default {
  data() {
    return {
      code: '',
    };
  },
  components: {
    Code,
  },
  mounted() {
    document.addEventListener('keydown', this.onKeyDown);
  },
  beforeDestroy() {
    document.removeEventListener('keydown', this.onKeyDown);
  },
  methods: {
    onKeyDown(event) {
      let r = Math.floor(Math.random() * codes.length);
      let rf = r % 5;
      let breaker = ""
      if (0.8 < Math.random()) {
        breaker = "<br />"
      }
      this.code +=
        "<font color='" + colors[rf] + "'>" + codes[r] + '</font>' + breaker;
    },
  },
};
</script>

<style>
body {
  margin: 0;
  background: #000;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #fff;
  background: #000;
  margin-top: 0px;
  height: auto;
  width: 100vw;
  overflow: hidden;
  word-wrap: break-word;
}
</style>
