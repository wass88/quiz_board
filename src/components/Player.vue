<template>
    <div class="main"
         :style="{
             backgroundColor: color
         }">
      <h2>{{ name }}</h2>
      <p class="score">{{ score }}</p>
    </div>
</template>

<script>
export default {
  name: 'Player',
  props: {
    name: String,
    color: String,
    score: Number,
  },
  data() {
    return {
    };
  },
};
</script>

<style scoped>
h2 {
  font-size: 20px;
  margin: 10px 0 0 0;
}
.score {
  font-size: 30px;
  margin: 10px;
}
.main {
  width: 100px;
  box-sizing: border-box;
}
</style>
