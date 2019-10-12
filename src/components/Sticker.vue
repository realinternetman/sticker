<template>
  <div class="hello">
    <div v-for="filename in filenames" :key="filename">
      <ul v-for="row in totalRow" v-bind:key="row">
        <li v-for="col in totalCol" v-bind:key="col">
          <img :src="imgSrc(filename)" :width="imgWidth" class="border" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data: function() {
    return {
      filenames: ["img.png"],
      totalRow: 5,
      totalCol: 3,
      imgWidth: 180
    };
  },
  computed: {},
  methods: {
    imgSrc: function(filename) {
      return require(`../assets/${filename}`);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  list-style-type: none;
  padding: 0px;
  margin: 0px;
}
li {
  display: inline-block;
  margin: 10px 0px 0px 15px;
  padding: 0px;
}
.border {
  border: solid 1px;
  border-color: #dcdcdc;
}
img {
  margin: 0px;
  padding: 0px;
}
a {
  color: #42b983;
}
</style>
