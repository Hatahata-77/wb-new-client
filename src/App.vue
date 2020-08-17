<template>
     <div id="app">
        <!-- START NAV -->
        <nav class="navbar container">
          <div class="container">
            <div class="navbar-brand">
              <a class="navbar-item" href="#">
                <h1>ヘルスケアソリューションカンパニー</h1>
              </a>
              <span class="navbar-burger burger" data-target="navbarMenu">
                <span></span>
                <span></span>
                <span></span>
              </span>
            </div>
            <div id="navbarMenu" class="navbar-menu">
              <div class="navbar-end">
                <a class="navbar-item">
                  管理本部
                </a>
                <a class="navbar-item">
                  営業本部
                </a>
                <a class="navbar-item">
                  公共
                </a>
                <div class="navbar-item has-dropdown is-hoverable">
                  <a class="navbar-link">
                    ヘルスケア
                  </a>
                  <div class="navbar-dropdown">
                      <a class="navbar-item">
                      3-3・4
                      </a>
                      <a class="navbar-item">
                      3-5・6
                      </a>
                      <a class="navbar-item">
                      東京本社
                      </a>
                      <hr class="navbar-divider">
                      <a class="navbar-item">
                      大阪支社
                      </a>
                  </div>
                </div>
                <a class="navbar-item">
                  クラウド
                </a>
                <a class="navbar-item">
                  ビジネス
                </a>
                <a class="navbar-item">
                  ビジネス
                </a>
              </div>
            </div>
          </div>
        </nav>
        <!-- END NAV -->
        <main>
            <div class="container">
              <div class="columns">
              <section class="column is-full">
                <div>
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
                </div>
              </section>
              <aside class="column is-narrow-widescreen">
                <p class="menu-label">社内システム</p>
                <ul class="menu-list">
                  <li><a href="*" alt="*">Bizion</a></li>
                  <li><a href="*" alt="*">TimePro</a></li>
                  <li><a href="*" alt="*">Grandit</a></li>
                  <li><a href="*" alt="*"></a></li>
                  <li><a href="*" alt="*"></a></li>
                  <li><a href="*" alt="*"></a></li>
                  <li><a href="*" alt="*"></a></li>
                  <li><a href="*" alt="*"></a></li>
                  <li><a href="*" alt="*"></a></li>
                  <li><a href="*" alt="*"></a></li>
                </ul>
                <p class="menu-label">お役立ちリンク</p>
                <ul class="menu-list">
                  <li><a href="*" alt="*">あいうえお</a></li>
                  <li><a href="*" alt="*">かきくけこ</a></li>
                  <li><a href="*" alt="*">さしすせそ</a></li>
                  <li><a href="*" alt="*">たちつてと</a></li>
                  <li><a href="*" alt="*">なにぬねの</a></li>
                </ul>
              </aside>
              </div>
            </div>
        </main>
    </div>
</template>

<script>
import Island from './components/Island.vue'
import 'whatwg-fetch'
import Axios from 'axios'

if (window.fetch === undefined) {
  window.fetch = fetch;
}

export default {
  name: 'App',
  components: {
    Island
  },
  data: function(){
    return {
      data: null
    }
  },
  created: function(){
    Axios.get('http://localhost:9998/api/wb/')
    .then(response => {
      this.data = response
    })
    .catch( error => this.error = error)
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
}
table.island{
    border-collapse: collapse;
    margin-left: 5px;
}
table.island tbody tr td{
    width: 130px;
    height: 80px;
}
.container{
  width: 1216px;
}
.wb-phone{
  font-size: 0.9em;
}
.wb-status{
  font-size: 0.9em;
}

aside {
  width: 200px;
}
:root {
  --bg: #071e36;
  --card-bg: #041221;
}
.navbar {
  background: var(--card-bg);
}

.navbar-item {
  color: ghostwhite;
}
.title.no-padding {
  margin-bottom: 0 !important;
}
</style>
