<template>
    <div>
      <h2>Cadastro de Filmes</h2>
      <form @submit.prevent="addMovie">
        <div>
          <label for="title">Título:</label>
          <input v-model="newMovie.title" type="text" id="title" required />
        </div>
        <div>
          <label for="genre">Gênero:</label>
          <input v-model="newMovie.genre" type="text" id="genre" required />
        </div>
        <div>
          <label for="autor">Autor:</label>
          <input v-model="newMovie.autor" type="text" id="autor" required />
        </div>
        <div>
          <label for="year">Ano:</label>
          <input v-model="newMovie.year" type="number" id="year" required />
        </div>
        <button type="submit">Adicionar Filme</button>
      </form>
  
      <h3>Lista de Filmes</h3>
      <p v-if="movies.length === 0">Nenhum filme adicionado</p>
      <ul v-else>
        <li v-for="(movie, index) in movies" :key="index">
          {{ movie.title }} -- {{ movie.genre }} ({{ movie.autor }}, {{ movie.year }})
          <button @click="removeMovie(index)">Remover</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newMovie: {
          title: '',
          genre: '',
          autor: '',
          year: ''
        },
        movies: []
      };
    },
    methods: {
      addMovie() {
        if (this.newMovie.title && this.newMovie.genre && this.newMovie.autor && this.newMovie.year) {
          this.movies.push({ ...this.newMovie });
          this.newMovie.title = '';
          this.newMovie.genre = '';
          this.newMovie.autor = '';
          this.newMovie.year = '';
        }
      },
      removeMovie(index) {
        this.movies.splice(index, 1);
      }
    }
  };
  </script>
  
  <style scoped>
  form div {
    margin-bottom: 0.6rem;
  }
  button {
    margin-top: 0.5rem;
  }
  </style>
  