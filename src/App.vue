
<template>
  <div class="">
    <div class="container p-3">
      <div class="card shadow">
        <div class="card-body">
          <nav>
            <router-link to="/">Home</router-link> |
            <router-link to="/tab_monters">Tab Monters</router-link>
          </nav>
        </div>
      </div>
    </div>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.bg {
  height: 100vh;
  width: 100vw;
  background-image: url("~@/assets/bg.png");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
</style>
