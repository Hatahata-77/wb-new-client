<template>
     <div id="app" class="container" style="padding-top: 64px;">
        <div class="container">
            <div class="error" v-if="error">
                {{ error }}
            </div>
            <section v-else>
                <!-- ３棟３階のレイアウト -->
                <div class="columns">
                    <Island v-bind:info="info" v-bind:ids="331"></Island>
                    <Island v-bind:info="info" v-bind:ids="332"></Island>
                    <Island v-bind:info="info" v-bind:ids="333"></Island>
                    <Island v-bind:info="info" v-bind:ids="334"></Island>
                    <Island v-bind:info="info" v-bind:ids="335"></Island>
                    <Island v-bind:info="info" v-bind:ids="336"></Island>
                    <Island v-bind:info="info" v-bind:ids="337"></Island>
                </div>

                <div style="height: 30px;">
                </div>

                <!-- ３棟４階のレイアウト -->
                <div class="columns">
                    <Island v-bind:info="info" v-bind:ids="341"></Island>
                    <Island v-bind:info="info" v-bind:ids="342"></Island>
                    <Island v-bind:info="info" v-bind:ids="343"></Island>
                    <Island v-bind:info="info" v-bind:ids="344"></Island>
                    <Island v-bind:info="info" v-bind:ids="345"></Island>
                    <Island v-bind:info="info" v-bind:ids="346"></Island>
                    <Island v-bind:info="info" v-bind:ids="347"></Island>
                </div>

            </section>
        </div>

    </div>
</template>

<script>
import Island from './components/Island.vue'
import 'whatwg-fetch'

if (window.fetch === undefined) {
  window.fetch = fetch;
}

export default {
  name: 'App',
  components: {
    Island
  }
}
</script>

<style lang="scss">
@import "../node_modules/bulma/bulma.sass";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
table.island{
    border-collapse: collapse;
    margin-left: 5px;
}
table.island tbody tr td{
    width: 100px;
    height: 50px;
}
</style>
