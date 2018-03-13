<template>
    <div class="main">
        <h1>春合宿クイズ大会2018</h1>
        <div class="boards">
            <Board v-for="q in quiz" :key="q.title"
                :title="q.title"
                :owns="q.owns"
                :colors="colors"
                class="board"
            ></Board>
        </div>
        <div class="players">
             <Player v-for="(p, i) in player_name" :key="p"
                 :name="p"
                 :color="colors(i)"
                 :score="0"
             ></Player>
        </div>
    </div>
</template>

<script>
import Board from '@/components/Board';
import Player from '@/components/Player';

const makeQuiz = x => ({
  title: x,
  owns: [-1, -1, -1, -1, -1],
});

export default {
  name: 'Main',
  components: {
    Board,
    Player,
  },
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      colors(x) {
        switch (x) {
          case -1: return '#fff';
          case -2: return '#000';
          default: return this.player_color[x];
        }
      },
      player_color: ['#0f0', '#111'],
      player_name: ['チーム1', 'チーム2'],
      quiz: [
        makeQuiz('情報'),
        makeQuiz('芸能'),
        makeQuiz('芸能2'),
        makeQuiz('芸能3'),
        makeQuiz('芸能4'),
        makeQuiz('kurimotz'),
        makeQuiz('wass80'),
        makeQuiz('karakasa'),
        makeQuiz('gire'),
      ],
      colorfrom_pos: {
        top: 0,
        bottom: 0,
        show: false,
      },
    };
  },
  methods: {
  },
};
</script>

<style scoped>
h1 {
  margin: 10px 0;
}
.main {
  width: 100%;
}
.boards {
  display: flex;
  flex-wrap: wrap;
}
.players {
  display: flex;
  flex-wrap: wrap;
}
</style>
