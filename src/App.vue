<script>
export default {
  data() {
    return {
      scoreone: 0,
      scoretwo:0,
      playing: false,
      com1: "",
      com2: "",
      result: "",
      gameOver: false,
      heartchoice:"src/img/heart.png"
    };
  },
  methods: {
    playGame() {
      const choices = ["src/img/rock.png", "src/img/paper.png", "src/img/cut.png","src/img/heart.png"];
      this.com1 = choices[Math.floor(Math.random() * choices.length)];
      this.com2 = choices[Math.floor(Math.random() * choices.length)];
      this.calculateResult();
      this.playing = true;
    },
    calculateResult() {
      if (this.com1 === this.com2) {
        this.result = "Tie...";
      }else if(this.com1 === "src/img/heart.png"){
        this.result = "Red Win!!!";
        this.scoreone += 1;
      }
      else if(this.com2 === "src/img/heart.png"){
        this.result = "Blue win!!!";
        this.scoretwo += 1;
      }
      else if (
        (this.com1 === "src/img/rock.png" && this.com2 === "src/img/cut.png") ||
        (this.com1 === "src/img/paper.png" && this.com2 === "src/img/rock.png") ||
        (this.com1 === "src/img/cut.png" && this.com2 === "src/img/paper.png")
      ) {
        this.result = "Red Win!!!";
        this.scoreone += 1;
        this.scoretwo += 0;
      } else {
        this.result = "Blue Win!!!";
        this.scoreone += 0;
        this.scoretwo += 1;
      }
    },
    resetGame() {
      this.playing = false;
      this.com1 = "";
      this.com2 = "";
      this.result = "";
      this.gameOver = false;
      this.scoreone = 0;
      this.scoretwo = 0;
    },
  },
};
</script>
<template>
    <div>
      <h1>ปายิงเยา...ปั๊กเป่ายิ๊งฉุบ</h1>
      <button @click="playGame" :disabled="gameOver">เริ่มเล่น</button>
      <button @click="resetGame" :disabled="gameOver" >เริ่มใหม่</button>
    </div>
    <div v-if="playing">
        <div class="img-resize1">score red: {{ scoreone }}<br><img :src="com1" alt="player one Choice"></div>
        <div class="img-resize2">score blue: {{ scoretwo }}<br><img :src="com2" alt="player two Choice"> </div>
        <br>
        <h3 class="result">ผล: {{ result }}</h3>
    </div>

</template>




<style scoped>
h1,h3{
  color:aliceblue;
}
div {
  width: auto;
  padding: 20px;
  margin: 20px;
}
button{
  padding: 10px;
  margin: 10px;
}
.result{
  text-align: center;
  width: auto;
  padding: 20px;
  margin: 20px;
}
div.img-resize1 img {
width: 64px;
height: auto;
}
div.img-resize1{
  border-radius: 25px;
  background: #ad2121;
  color:aliceblue;
  padding: 20px;
  width: 200px;
  height: 150px;
  float: left;
}
div.img-resize2 img {
width: 64px;
height: auto;
}
div.img-resize2{
  border-radius: 25px;
  background: #212fad;
  color:aliceblue;
  padding: 20px;
  width: 200px;
  height: 150px;
  float: right;
}
</style>