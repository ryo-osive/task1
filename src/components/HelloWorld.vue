<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="row text-center">
      <div class="col" style="">
        <label>TEXT-1</label>
        <input
          type="text"
          id="txt1"
          class="form-control"
          style="  max-width: 250px; margin: auto;"
          v-model="txt1"
        />
      </div>

      <div class="col" style="margin: auto; ">
        <label>TEXT-2</label>
        <input
          type="text"
          id="txt2"
          class="form-control"
          style="  max-width: 250px; margin: auto;"
          v-model="txt2"
        />
      </div>
    </div>
    <div class="col">
      <button @click="calc">Compare</button>
      <br />
      <br />
    </div>
    <label>OUTPUT</label>
    <br />
    <br />
    <p>
      <span v-html="result"></span>
    </p>
  </div>
</template>

<script>
export default {
  name: "taskCompare",
  props: {
    msg: String,
  },
  data() {
    return {
      txt1: "",
      txt2: "",
      result: "",
    };
  },
  methods: {
    calc() {
      var t1 = this.txt1.split(" ");
      var t2 = this.txt2.split(" ");
      var output = "";
      console.log(t1);
      console.log(t1.length);
      var i;
      for (i = 0; i < t1.length; i++) {
        if (t1[i] == t2[i]) {
          output = output + t1[i];
        } else {
          output =
            output +
            " <span style='background-color: #FFFF00'>" +
            t1[i] +
            " </span>";
        }
      }
      this.result = output;
    },
  },
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
</style>
