<template>
  <div class="home">
    <div
      v-for="index in Array.from(Array(27).keys())"
      :key="index"
      :class="`box ${checkColor(getValue(index))}`"
    >
      {{ getValue(index) }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data: () => {
    return {
      arr: [
        [0, 7],
        [1, 8],
        [5, 19],
        [6, 22],
        [7, 25],
        [11, 37],
        [12, 47],
        [13, 48],
        [16, 50],
        [17, 57],
        [18, 65],
        [22, 78],
        [23, 79],
        [24, 81],
        [26, 89],
      ],
      coloredArr: [19, 65, 37],
    };
  },
  methods: {
    getValue(index) {
      const indexValue = this.arr.find((value) => value[0] === index);
      if (indexValue) {
        return indexValue[1];
      } else {
        return "";
      }
    },
    checkColor(value) {
      if (this.coloredArr.includes(value)) {
        return "red";
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.home {
  width: 60vw;
  height: 30vh;
  margin: auto;
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
}
.box {
  height: 33.33%;
  width: 11.11%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  &:nth-child(odd) {
    background-color: yellow;
    color: black;
  }
  &:nth-child(even) {
    background-color: black;
  }
}
.red {
  background: red !important;
  color: white !important;
}
@media screen and (max-width: 700px) {
  .home {
    width: 100vw;
  }
}
</style>
