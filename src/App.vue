<template>
  <h1 class="text-center mt-5">Search Rick and Morty</h1>
  <MyComponent />
</template>

<script>
import MyComponent from "./components/MyComponent";

export default {
  components: {
    MyComponent,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Irish+Grover&family=Kanit&family=Yanone+Kaffeesatz:wght@500&display=swap");
body {
  background: #2bc0e4; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #eaecc6,
    #2bc0e4
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #eaecc6, #2bc0e4);
  font-family: "Irish Grover", cursive;

  font-family: "Kanit", sans-serif;

  font-family: "Yanone Kaffeesatz", sans-serif;
}
h1 {
  font-size: 80px;
}
</style>
