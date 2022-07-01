<template >
  <div class="home">
    <div class="container">
      <div class="row mt-5">
        <div class="col-md-6">
          <div class="card shadow">
            <div class="card-header">
              <h1>Numbers Survival</h1>
            </div>
            <div class="card-body">
              <h4>Lv. {{ Lv }} ช่วง 1 - {{ 50 * Lv - Stack }} คะแนน {{ score }}</h4>
              <h4>Hp: {{ Hp }}</h4>
              <input type="number" v-model="number">
              <button @click="actNumber">OK</button>
              <h4>{{ status }}</h4>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <div class="card shadow">
            <div class="card-header">
              <h1> <img src="~@/assets/shop.png" alt="" class="shop-logo shadow"> Shop</h1>
            </div>
            <div class="card-body">
              <h5>red potion : - 80 Score</h5>
              <input type="number" v-model="Item1">
              <h5>number potion : - 70 Score</h5>
              <input type="number" v-model="Item2">
              <br>
              <br>
              <button @click="buy">Buy</button>
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
  name: 'HomeView',
  components: {
  },
  data() {
    return {
      number: 0,
      ans: Math.ceil(Math.random() * 50),
      status: "comeon !!!",
      score: 0,
      Lv: 1,
      Hp: 100,
      Item1: 0,
      Item2: 0,
      Stack: 0,
    };
  },
  methods: {
    actNumber() {
      if (this.number > this.ans) {
        this.score -= this.Lv
        this.Hp -= (2 * this.Lv)
        this.status = "มากกว่านะครับ กรุณาลดค่าตัวเลข"
      } else if (this.number < this.ans) {
        this.score -= this.Lv
        this.Hp -= (2 * this.Lv)
        this.status = "น้อยกว่านะครับ กรุณาเพิ่มค่าตัวเลข"
      } else {
        this.Lv++
        this.ans = Math.ceil(Math.random() * (50 * this.Lv))
        this.score += 20 * this.Lv
        this.status = "ถูกต้องแล้วครับ"
      }
    },
    buy() {
      if (this.score >= ((this.Item1 * 80) + (this.Item2 * 70))) {
        this.score -= (this.Item1 * 80) + (this.Item2 * 70)
        this.Hp += (25 * this.Item1)
        this.Stack += 20 * this.Item2
        this.ans = Math.ceil(Math.random() * (50 * this.Lv) - this.Stack)

      }
    }
  }

}
</script>
<style>
  .shop-logo{
    width: 100px;
    height: auto;
  }
</style>
