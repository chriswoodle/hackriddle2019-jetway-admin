<template>
  <div class="person"></div>
</template>


<script>
const firstRowScale = 15;
const firstRows = 5;
const rowScale = 13.45;
const seatScale = 9;
const seatLetters = ["A", "B", "C", "D", "E", "F"];
const seatValues = [-3, -2, -1, 1, 2, 3];

export default {
  name: "my-component",
  props: ["seat"],
  data() {
    return {};
  },
  mounted() {
    console.log(this.seat.split(":"));
    setTimeout(() => {
      const row = parseInt(this.seat.split(":")[0]);
      const x =
        value_limit(row, 0, firstRows) * firstRowScale +
        value_limit(row - firstRows, 0, 100) * rowScale +
        (row > 5 ? 5 : 0) +
        (row > 14 ? 3 : 0);
      const y =
        seatValues[seatLetters.indexOf(this.seat.split(":")[1])] * seatScale;

      const targets = this.$el;
      this.$anime
        .timeline({
          easing: "easeOutExpo",
          duration: 2000
        })
        .add({
          targets,
          translateY: 473 / 2,
          easing: "easeOutExpo"
        })
        .add({
          targets,
          translateX: 0 - x,
          easing: "easeOutExpo"
        })
        .add({
          targets,
          translateY: y + 473 / 2,
          easing: "easeOutExpo"
        });
    }, 2000);
  }
};

function value_limit(val, min, max) {
  return val < min ? min : val > max ? max : val;
}
</script>
<style lang="scss" scoped>
$circleSize: 8px;
.person {
  height: $circleSize;
  width: $circleSize;
  background-color: red;
  border-radius: 50%;
  margin-top: -($circleSize/2 - 2px);
  margin-left: 660px;
  position: absolute;
}
</style>
