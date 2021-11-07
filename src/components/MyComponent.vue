<template>
  <div class="my-5 d-flex justify-content-center">
    <input
      v-model="search"
      class="form-control m-3"
      style="width: 300px"
      type="text"
      placeholder="Ingresa nombre del personaje"
    />
    <button class="btn btn-outline-dark m-3" v-on:click="searchCharacter">
      Buscar
    </button>
  </div>

  <div class="container text-center mt-5">
    <div class="row d-flex justify-content-center">
      <div
        v-for="character of characters"
        :key="character.id"
        class="col-4 d-flex justify-content-center mt-5"
      >
        <div class="card">
          <img v-bind:src="character.image" class="card-img-fluid" />

          <div class="card-body">
            <h4 class="card-text">{{ character.name }}</h4>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
const url = "https://rickandmortyapi.com/api/character/";

export default {
  data() {
    return {
      characters: [],
      search: "",
    };
  },

  methods: {
    async get() {
      const params = {
        name: this.search,
      };

      try {
        const { data } = await axios.get(url, { params });
        this.characters = data.results;
        console.log(data);
      } catch (error) {
        console.log(error);
      }
    },

    async searchCharacter() {
      this.get();
      const result = this.characters.filter(
        (character) => character.name === this.search
      );
      this.search = "";

      console.log(result);

      console.log(this.search);
    },
  },

  created() {
    this.get();
  },
};
</script>

<style>
.card {
  width: 250px;
  height: 300px;
  padding: 25px;
}
</style>
