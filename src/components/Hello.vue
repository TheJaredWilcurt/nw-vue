<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <h2>Versions</h2>
    <div>
      You are using
      <ul>
        <li>Vue.js v{{ versions.vue }}</li>
        <li>NW.js v{{ versions.nw }}</li>
        <li>Node.js v{{ versions.node }}</li>
        <li>Chromium v{{ versions.chromium }}</li>
      </ul>
    </div>

    <h2>Operating Systems Support</h2>
    <ul>
      <li v-if="osSupport">Windows XP+, OSX 10.6+, Ubuntu 10+</li>
      <li v-else>Windows 7+, OSX 10.9+, Ubuntu 14+</li>
      <li>Older OS versions, and other Linux distros (especially Debian based) may also work.</li>
    </ul>

    <h2>Documentation</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Vue.js Docs</a></li>
      <li><a href="http://docs.nwjs.io" target="_blank">NW.js Docs</a></li>
    </ul>

    <h2>Support</h2>
    <ul>
      <li><a href="https://vue-land.js.org" target="_blank">Vue.js Discord Chat</a></li>
      <li><a href="https://gitter.im/nwjs/nw.js" target="_blank">NW.js Gitter Chat</a></li>
      <li><a href="https://gitter.im/vuejs/vue">Vue.js Gitter Chat</a></li>
    </ul>

    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js Desktop App',
      versions: {
        vue: require('Vue').version,
        nw: window.nw.process.versions.nw,
        node: window.nw.process.versions.node,
        chromium: window.nw.process.versions.chromium
      },
      osSupport: function () {
        var nwVersion = window.nw.process.versions.nw
        return nwVersion.startsWith('0.14') || nwVersion.startsWith('0.13') || nwVersion.startsWith('0.12')
      }
    }
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
