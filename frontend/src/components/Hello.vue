<script setup>
import { ref } from "vue";
import axios from "axios";

const text = ref("");
const fechPidor = () => {
  let config = {
    method: "get",
    maxBodyLength: Infinity,
    url: "http://localhost:3000/hello",
    headers: {},
  };

  axios
    .request(config)
    .then((response) => {
      console.log(response.data);
      text.value = response.data;
    })
    .catch((error) => {
      console.log(error);
    });
};
fechPidor();
const count = ref(0);
</script>

<template>
  <div>Вайт + Вуе</div>

  <button type="button" @click="count++">{{ text }} {{ count }}</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
