<template>
  <div>
    <div
      class="card"
      v-for="(item, i) in images"
      :key="i"
      :style="{ backgroundColor: cardColor }"
    >
      <div class="cardStrip" :style="{ backgroundColor: stripColor }"></div>
      <div class="imgBx">
        <img :src="require('@/assets/' + item.src)" :alt="item.src" />
      </div>

      <div class="contentBx">
        <h3 :style="customTextColor">{{ item.title | titleLength }}</h3>
        <h2 class="price" :style="customTextColor">{{ item.price }}</h2>
      </div>

      <div class="btnBx">
        <a
          :href="item.url"
          class="buy"
          type="button"
          @mouseenter="updateHoverState(true)"
          @mouseleave="updateHoverState(false)"
          :style="[customButtonColor, customTextColor]"
          >{{ item.btnText }}
        </a>
      </div>
      <h1 class="cardContent" v-show="numberShow">{{ i }}</h1>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      button: {
        colorBackground: "#000",
        text: "#fff",
      },
      hoverState: false,
    };
  },
  computed: {
    customButtonColor() {
      // let  modifier = "";
      // if (this.hoverState)   modifier = "Hover";
      return {
        backgroundColor: this.button["colorBackground"],
      };
    },
    customTextColor() {
      return {
        color: this.button["text"],
      };
    },
  },
  methods: {
    updateHoverState(isHover) {
      this.hoverState = isHover;
    },
  },
  filters: {
    titleLength(value) {
      if (value.length > 33) {
        return value.slice(0, 32);
      }
      return value;
    },
  },
  props: {
    images: {
      type: Array,
      required: true,
    },
    cardColor: {
      type: String,
      required: true,
    },
    stripColor: {
      type: String,
      required: true,
    },
    buttonColor: {
      type: String,
      required: true,
    },
    textColor: {
      type: String,
      required: false,
    },
    numberShow: {
      type: Boolean,
      required: false,
      default: true,
    },
  },
  mounted() {
    this.button.colorBackground = this.buttonColor;
    this.button.text = this.textColor;
  },
};
</script>

<style >
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");

* {
  margin: 0;
  padding: 0;
  font-family: "Poppins", sans-serif;
}

body {
  display: flex;
  justify-content: center;
  width:100%;
  min-height: 100vh;
}
.card {
 
  position: relative;
  width: 320px;
  height: 420px;
  background: #122936;
  border-radius: 20px;
  overflow: hidden;
  float: left;
  margin: 20px;
}
.cardStrip {
  position: absolute;
  top: -50%;
  width: 100%;
  height: 100%;
  background: #2e9969;
  transform: skewY(320deg);
  transition: 0.4s ease;
}
.card:hover .cardStrip {
  transform: skewY(400deg);
}

.card .imgBx {
  position: relative;
  width: 100%;
  height:230px;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 20px;
  z-index: 1;
}
.card .imgBx img {
  max-width: 55%;
  transition: 0.5s;
}
.card:hover .imgBx img {
  max-width: 50%;
}
.card .contentBx {
  position: relative;
  padding: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  z-index: 1;
}
.card .contentBx h3 {
  width: 100%;
  font-size: 18px;
  color: #fff;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-size: 1.5rem;
  word-wrap: break-word;
  text-align: center;
}
.card .contentBx .price {
  text-align: center;
  font-size: 24px;
  color: #fff;
  font-weight: 500;
  letter-spacing: 1px;
}
.card .btnBx {
  display: flex;
  justify-content: center;
  align-items: center;
}
.card .btnBx .buy {
  position: absolute;
  top: 430px;
  opacity: 0;
  padding: 10px 50px;
  color: #fff;
  text-decoration: none;
  background: #2e9969;
  border-radius: 30px;
  text-transform: uppercase;
  letter-spacing: 1px;
  transition: 0.5s;
  z-index: 1;
  margin: 10px;
}

.card:hover .btnBx .buy {
  top: 340px;
  opacity: 1;
}
.card .btnBx .buy:hover {
  padding: 10px 70px;
}
.card .cardContent {
  position: absolute;
  bottom: -20px;
  right: 5px;
  font-size: 7rem;
  font-weight: 600;
  color: rgba(0, 0, 0, 0.2);
}
</style>