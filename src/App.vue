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
      const choices = ["data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAP8AAADGCAMAAAAqo6adAAAAjVBMVEX///8AAADu7u7t7e36+vrz8/Py8vL4+Pj8/Pzq6urAwMDj4+Pe3t7Pz895eXnW1taZmZldXV1lZWVtbW1XV1fKysqGhoagoKA1NTW2trarq6tMTEy8vLzZ2dmUlJQuLi4QEBBJSUmDg4NCQkIbGxufn58xMTE8PDyEhIQkJCRxcXEMDAwgICCOjo4XFxfEJFtEAAATJElEQVR4nO1daWOjLNc2KoImZjepZmvSprmbmfT//7zXjVVQNC7pPO81XxxLlAvhbBzAMBLYlmmalp1eJ5cmSC9Bcmn90yWMl63Z//P/3+OPnBgmGpy/lf/GUj61xRLQAQDCmLvrjmeHGFmRuCFI3burh2EngCABTK/TSyBedlICxl8aAT98TBenzxGDz9PisfWsuBzquB6GlQA3kWWRJkqQN2LrJUwrKzGJ/lv/GanxdQknEDid1SOGYQ4w3OMOj/zjroQ5xdvDz37XiUAw++cPoRM8zlrcc5zm7r/DH4bLOtxzLPyu+BdHRPabsjHTrIQJDSdaNyCf4uZBp4uaKmQmlbsOer5ELHfjF4aNyad48w3Uek0NaRdpW/+bhuHfdTh+/i3TBwvHQG3r/xYGUaW4h+Prp5rV3/P0Gvpjh1YHjP3osXuXlI1SefWr7F/H9lcq6qdp5DO8BUyioqjcueB38bf3H3Luu7kPldQJ/Kn4Ow+aZvv82xf3WYnwJP3uD599fSmQd+Z/PIct1rRD/Rc7c1uZNFtHri73HBN+AF3arGmJ/VPdzUpLGJFE6O1CUJN8ivGCfcgKtVXTDu0/77tA/rZVC7sqBH+ZBy1hSzXtjP+sKPUuk8bkU/zH9gDYIn9LbiJY9Dc1SwCnoPHeQvQc+xg+25iwlZqaBmMLwrJQhWaJ5AIeRfaL2dPkEzg3+sgIPVnT7LaRN1GL+s8XB/503Ar7BIwHMTHcNvRffqct+8eAop1/aS7zJKAD691uQ3S1zN/2RPZmm+xjUJN4ab8af8cS5N69bfYGOwQi0B7/Fsa/CQPeZdvVUHgzbbMIUfHims+P/2TGwQEoAUiv00uYXkI7udYsAQ1e7H97+uwNZEShblmXdi/DblJTtkTmT1d2omKJpOHYEo555ujPa7BPEe50BeWe0QEaNS0r0cT+i6sJrZm3DyZW7sDGJWDAsV83GPjBKNIsSaTMrnf71wHAe2Az5M/umkemYcTR39dnHw+Bw2in5xna5EVBq/zVQTQSuz9ceAk/WgeGYQIuSrFs5OLFmIxGW62CIX7VTcmukktu/9biP5HF7tcu4AK72oJM2gA3LWOReFe+GBCtyz8votYZLi7hWOK3x3hjrm9Wc/ppA4weGuVmpPGRpKbVXOrbvyYUTTspdCpf1QCfQXU50uMmhZp2Yv8hsNGhX0fnqxtgtHQTeViGA37jph/+QBHF5XCqG9hTNsDoURUfJR0AdcC/EERw/4pU1+tCfGvRAvsY4+xpFZqAjMaQr2mT/A9IQwTMJb62bXTgeP49ZuEM2+Oikpd26McNkEeNo9IhgEPLO4OpaTUX/rbN2b+KRgRs4Gl0YsY4ZO5vq4asPsyf/JnzkhmSK37xpMbnFkvo2H/OjKXP2qiQCXA/ofVFIAOSQNddGTkzcZE56Nb+HTPseR+FkYleax8/AzW0TkeFRYQl4M3ulD9i5nCOijqONDR2TcyZVv9+zCTqgLiBB5whlbikred/MCx5t2beJX0+2h1jPQ9Et4IMABskc+aHWeAfTMAYhDoBETZEgIohAntLq+Bzb2cc3uetHhlQcdp8sYmCsYn7Ao60vm0WjHq+rbaBGVfejv+VBkTSayNvIrmINJ0JS58d4g79Q9Ty2CcIZCkQMf5+fayXq2lJOs06AgUuTew/cCaPFPo4/UPtSE8NXAvMtLEMnrd/AQ1rCLEZWrFVh/RjFTuXcdPDmwed5/jTTj7lq0V14q1T+jFQ9CYjp4VbAPX6f6oLsjuMQkQP/KCTUCmq+Vud3VHgsPmR0tPANJZ/6TM4X56yLdN/Jv38B17E0WHRheaTNsFcL124gL9jo1T/ldg/gHx+rvcjxuzf9EQ/fa9/XRVzKgg+T19f37J+EsKG9h+daBAsDxLtFIdF9wBjL9osd1w7fE8jH4fi478fz0IDHGEj/oDM5wgajgq/JzM6ngKyxpPDbOZLEghhyA+WDdS2f5k1Aw4x/IXHE4v4v+7YPQs+ZeyoTpnLYgEZmGsAbBJkFyIx9PP3TaoWxmwfiFCBYWX+B9Fxgu9FEhxadPk7ATsnNYF18z9IzEsIaROp+NYTjeYYU3XwU9v+I5MdwlQmkYrdeH2tgsaRRnd5yqBRuJPzR/iHS+GZ+P5XPxSeQWyz0QYInFr5HyS6wnv9Qtz55WGTyMAbNPXzP2wbO9ffwgOJ090vj8ag2sozVPkfkuku8jPB9rHw/aP4olcF0QKJp6pr/xkk7CVIP3K/jamufkDsgFkN/uf8NzvhYXg5w7pHAk+CdOW7fv4H8XxDxbN+h/TLQOx1VJH/kbVIAjJoBM/vSB9F4VodxT9bApm/ChRsC/oPYikvdnOsTpmgX7ow4WN19SYay5mGwVde62nGvNr+JTauEPUk3Z/aflze2256DL2J82oNgWOob1nFKu0/hxg/gm9NpD/t8F8jCT5vu8X0ON9Gnj+buIM3B3FlspnESv4QB3g+hAdhVUK7PyySl2HXV5xQDlyNPG+hkj8OLwnGD8DPYSYC9fgPrDDOXCU4/nksALIgw/zAP4bY/kyP1l7NP+QowJXMwyAMW2n+B478/BEeg4fFmblnSahKMeQIwL78Fghs5fYfjvCIU1vY+LuyN8FFb35myHABDuTPgZb9i31GQfsRrSiGfdHEm9+rWqGPiSIV6vEnPIXEEzws3hVvsSb7JDYvpsplGNRfxAM3KvKXzH9h7a8a/pUzvvbYD/bR8XG5rz9On0kY/Y9eXndXwHl6e0ee/2GnsQA7y/+AWFqIkS8cTdRdpoABzaGdZSy4PENkm/2d0//wXDH821vO2BOIkZYJrnL7xyRWjpB6R4zinmrdHrDd8q4T/3VI4pVgseAEcHFYvD6w4Frr+D8O9v3FADc2/ocVZU1AdBD2fwX+yDaT1MHkDjIg/s5TxVPaWcvdI8hE5iy1QRi2hmxGdC3/ziQTbnB3ti6wZfapl/+BnT9h4gO3YucJT22DyO25TvyXin8h8q0aFi8PkqTuavEnzq/wmHN+u671MzTIuqXEbK3Of3awsjwLz/ml4o+mUSdmW3H8QwEoYpqLAbH+ePE3/xmdHi/cJDSFb1WgmsY/UrARYWwsCA4baUfuLnYspl7Veq0hgNjw7NjUy/8gsSL+WbhbcIu82OD3OnpBv4DmAKWuv479i9N+hHgN3n2Iy3gU1kT+TL3XMg4o/bO4ZZaSP/6FEOTBPZ2L40rWhH4cg1dpA5eZm3C09//AvxB8duxCc2FMxZLgj8cLtAFit+PwNfb/MNKMCOIrC/E6ebOol2DcLuGQ8gBw6wbm0EzDHYYpsC3kfzjE/OHndIkeESaEH6MyLObBEGFPV9hmd6NcIVew/+iCH/6ReA6ZTwdK2sjflG3ZGv9iuS3Z47NtjL3jWtx2cFoj/5ks9hSCn1jTiTOC2Uu359ImiLHsvCeAWXiRrhF42KYm/2TqF9s57/zTsfpXBX/Avnp/3+9FcQ1fO8yjx0K6z2gKX5H/n83/CBlhZK3zD/8OLEzL9neYbDU2eP68b9uKBgM3CI/3W+UrNxCHexn5h/PfUjAaAcu/d/5dWNNXLHZDvs46lSddSHPmbR/LW8mWygKSLBbd/e8U7i9Opy+vOtJsg6YOE/I2OvtQFHDTX/9G5nP5N+OerTuLeYjuJWu27g35xwDBfKF+sApnbf4k75mXVLjZhaBYKay4qvIVrFItUgOuN19KE29SnNaXrRduuAnZpVHX/uelFBavtXuuFRwXBQPhie/PwPX328dlulzv1uv14n7ZHLf7gMlCG7PG2RVaUv6FgMAfKVMcFBUyQnRr6s25RugrYGIxgmhiS+MfabdgNCJJ/eMTdvCktuAVul6gHfhwgvk6Gw49hhCph5rG86r3/yBbmfGaHisb3qeZ1mbj7ue1t/9+CnQMJKK7Ov5Lpr/4+KeUf964pxeO/zHLtRLXRYM/yZblOraMP839uw/v7qtB1op6Wvt/kM0Fud0+ZOOf2RvilSdFyQf9UK32Nrj5z3NenHN1ZPLfZfiPTsNmeJaBLAU9ZOY+N/+Z3WE0IiBbO7AWEDYmOPuHd3fOzXRj9yAm/UYx/83nf5BuzQp23Cm4r2wKLshq6DwfBXBI/6TD34LY1v2SPEJQdmL4a/rU7o9dgUxTaOU/A5LlznR2lf87Pv+GFsCVy6Q0x7+Y/+YQucas/sDh1OLs915ogNFqyF0B5KAJvYX8N5lGIAKTGjaYpTgrnKBw3MHu1ZYG49yNT6i1/weRgNRPxUr0XfZ4t7BT1fsxyZ54mWVRRAPo5T8bZFATJ4jYenIRPxPFwGi0eKVOQDq0o8WfzuuSJBis6lRbW0uOuxltXmZGmCTAFvjLLULyOckmB7iLq9N/Qkni962FY1/aAFHfhTMUZUEBAOmWl1gHkBWRJW+RtUD7J2A0AU7pnqPK/I/kdFoL0a2uT1knJjKx1M7fy6LxdWKGHYEsgEj+o7P/B2ICl1M/7sQAx68q0n99yRxIV6z0gVV0mtSjtf+FX6SRo8q8cQtzwsNrgvr81VsPamzzLOy/NHzKoND/i/wl+/+odrvXit66R8Y3HN4xJgvgkv9w41/U/5m0TqaMYeHoyRwyG1hAovUCrHTEPRQGANbeW6Bl/2RdBG4VDaA7nsE1UYiLF0gNxGqpaP+U8LeMiXxR37v+i2feS9iAuOZ+Lf626vzSX7P5Sw7i0evu/8GIyEM+5fyzuFJX/0UDXSqQPL1sX8v0njz/A+9/REMEBkTQnYzTHxE/9xdt/5IAR69WdmX+h+ow28QqZnbEbHLC0XDAgziL3jU//5AxirpIZOoKJPyR+S7PnP9HPLzftAoQW7/vuXHzBH/qFvyiHZCwL7fSiv+bxQ0hmBLUKHzFQLcURG3t8/kvlr9y/1PZJQSQLih5NomnN5BMIUOy/6lZ/rkNsUMAagQ8e9ZVTwiZ+lbnf1SemQHpji+vO+XLgCS06a3/0zj/ccQ+8eVB8j/k6/8a8Kc6oP/9v2uDDtd0/V+Bv9zcKzcI6YRXS0d+dQeao5IG7pX5HwkK5x8ozgwwbZqE29qhX10AsSkqriPjkqHmIbIO89jhY3slYI6uinTX/5Xbf1kJwCx8fGFPiKnlUnv9nw5/LjT2slqQCeC+243Of1EbRGxw9AXmdyTYs/n3E+X5hxXnX8nOjMruMiH+18v/tCMubhcYyvOvmui/BMhhEvBfqgcgNxQ2JQxBo/NfygWCOf7DNvBgsK3k5Ld9tL3O58fHZVlcILNvdv5JlUBkz0brTwvEHdmN6YbXzXS1Vq8BofgzA2ouz/A3uYMxO7UDrPjjHh/TxflWcgCQHDtglHBpZv/iEtzBqJ1aguZVvb6xFFEVl/QUWPZEWOaSnhmrKMHNknfsC7g6qysF3Meogkv27EL+R3mHoCUg2wDfbscZb2h2VSwok2LqQsaWl3PB/Gvaf/SEQO5w3D4SHczgOtVYBPkROW2e/60+IXLCLuzqLSTmjIPo+t9y/SETiKdVvsaoB/6mM2YniT8GiArHFqk7Hk8mLp7lDm0HaXIx8js64l5eIm4BTjANOC+Aq+A72lye0f95CWQALlNkOdRiKBKVMLW5PGX/0BI2nykyUBdg9yful78JuWMQRutBAsPY61mV1bQb/qbjnrkW6PJQYAXIxoWRPheN/A/NgIgpLIP46T3pkTuaSJOLKv+jQUCkkDK663kdDH7vzbD1uRh5EzXXf7SE4wjrQJL1cL3lv5MNn7agBhcjv9Pc/mGj6jDkG6DH1WA0JO/W4WIU7jTmn6ZWFZJGpz2pAmKEXkrCHZ3zt5Dhi4sgelkPR3dfSmtXm7/F/MZipsiZA3G1SxSObF93Hh6kof65UYtLlv8BKsMddUqgceFQmFPUaRIwHXTfsDp0w96unf+hUcIyjVnRQ592lgUPGf8rcGpxac3+K5QIigG7r6iTpEHW7JjDejXtjn/sjkg26Fru27YHILvv3BLWrGmX/A0QyYK2yzAp2VIzIE7WrkHdmurEv93GJRwnlM5Q7LbtqESHdzli+s1q2pL9Ky0RKPaCWz29XXIgaJkFzu6sU1PMvy37p1ACwplqHdGfxTxoujjUKzz0AovZvf3bf5ISDjC3JbM3y+N+UksvgOB4Lj5mDxvVtAf+MRxjVr496Pd5Og/9qnaAh/18KW3K3Rg0q6mcf8sGUVoChRo7Y8be+/J+OUZh6AX+7HCYzWZ+4IXhdnNfqKc+3/eK3f2qa6qY/wOIXDqonRIo2Se3erPSBjgio3FN2xb3VSXErZlbYO8C84madmf/KEogN5zKj8hrgI/QruXu92n/lSgEOAmneqdGluF0HD9b00H4p+9N9NijuDOo/pefFzdzalKPnsc/b3cCcPCudy29wGJx9FwIzFbqURYiKEQL2i+BkIEQdIPwulm8Ve7o/PMxja0lGP+mrXoY0i7Shf5Xl0gMpCwQDyazINpuH9P7crHefdxifOwWi+XqctxGMzcpBJxW6yHn379AyEswcxIg+UxZYZTq7k7q8WL8ey+R8zcrf/OPlpDzl6x/+EdL/B/XCU2WcWg9bAAAAABJRU5ErkJggg==", "src/img/paper.png", "src/img/cut.png","src/img/heart.png"];
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
