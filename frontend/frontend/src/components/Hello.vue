<template>
  <div>
    <p>{{ msg }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Hello",
  data() {
    return {
      msg: "",
    };
  },
  methods: {
    getResponse() {
      const path = `http://127.0.0.1:5000/hello`;
      axios
        .get(path)
        .then((res) => {
          console.log(res.data);
          this.msg = res.data;
        })
        .catch((err) => console.log(err));
    },
  },
  created() {
    this.getResponse();
  },
};
</script>
