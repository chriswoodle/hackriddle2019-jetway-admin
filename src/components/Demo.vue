<template>
  <div class="hello">
    <person v-for="s of seats" v-bind:seat="s" v-bind:key="s"></person>
  </div>
</template>

<script>
import PersonComponent from "./Person.vue";
export default {
  name: "HelloWorld",
  props: {},
  data: () => {
    return {
      seats: [],
      tickets: ["1:A", "2:A", "3:A", "4:A", "5:A", "6:A", "7:A", "8:A", "9:A","10:A", "11:A", "12:A", "13:A", "14:A", "15:A", "16:A", "17:A", "18:A", "19:A", "20:A","21:A"]
    };
  },
  created: function() {
    setInterval(() => {
      const item = this.tickets.shift();
      console.log(item);
      if (item) {
        this.seats.push(item);
      }
    }, 1000);
  },
  components: {
    person: PersonComponent
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.hello {
  /* background-color: red;  */
}

.seat {
  background-color: blue;
  height: 50px;
  width: 50px;
}
</style>
