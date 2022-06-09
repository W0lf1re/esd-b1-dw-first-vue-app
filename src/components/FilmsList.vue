<script>
export default {
  name: "FilmList",
  props: ["filmsList"]
};
</script>

<style scoped>
li.off {
  background: red;
  color: white;
}
li.on {
  background: green;
  color: white;
}
</style>

<template>
  <ul>
    <li
      v-bind:class="{ off: !film.public, on: film.public }"
      v-for="film in filmsList"
      v-bind:key="film.title"
    >
      {{ film.title }}
      <!-- if public is false -->
      <!-- on click change value public -->
      <button v-on:click="() => this.$emit('handleUpdatePublic', film)">
        {{ film.public ? "Private" : "Public" }}
      </button>
      <!-- if public is true -->
      <!-- on click change value public -->
    </li>
  </ul>
</template>
