<template>
    <div class="main">
      <h2>{{ title }}</h2>
      <div class="cells">
          <div v-for="(own, i) in owns" :key="i"
              v-on:onclick="$emit('cell-click', clicked(i))"
              class="cell"
              :style="{
                background: colors(own),
                height: (scores[i] * 3 + 'px'),
                lineHeight: (scores[i] * 3 + 'px')
              }">
              {{ scores[i] }}
          </div>
        </div>
        <ColorForm
          :pos="colorform_pos"
        >
        </ColorForm>
    </div>
</template>

<script>
import ColorForm from '@/components/ColorForm';

export default {
  name: 'Board',
  components: {
    ColorForm,
  },
  props: {
    title: String,
    owns: Array,
    colors: Function,
  },
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      scores: [10, 40, 20, 30, 50],
    };
  },
  methods: {
    clicked(x) {
      return {
        num: x,
      };
    },
  },
};
</script>

<style scoped>
h2 {
  font-size: 30px;
  margin: 10px 0 0 0;
  height: 40px;
}
.main {
  width: 182px;
}
.cells {
  display: flex;
  height: 150px;
  flex-direction: column;
  flex-wrap: wrap;
  width: 180px;
  border: 1px solid #555;
}
.cell {
  border: 1px solid #ddd;
  width: 60px;
  font-size: 30px;
  box-sizing: border-box;
  position: relative;
}
</style>
