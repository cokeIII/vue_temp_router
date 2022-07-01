<template>
  <div class="about">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <div class="card shadow">
            <div class="card-body">
              <h1>Tap monters</h1>
              <div class="display" @click="tapDmg">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>
<script>
// @ is an alias to /src
export default {
  name: 'AboutView',
  components: {
  },
  data() {
    return {
      tap: 0
    };
  },
  methods: {
    tapDmg() {
      alert("tap")
    }
  }

}
</script>
<style>
.display {
  width: 400px;
  height: 300px;
  background-image: url("~@/assets/poring.png");
  background-repeat: no-repeat;
  background-position: center;
  position: absolute;
  /* background-color: brown; */
}
</style>
