<template>
    <div class="main"
       style="{
         position: 'absolute',
         top: pos.top,
         left: pos.left,
         display: pos.show ? 'block' : 'none',
       }"
    >
        <div v-for="(tname, i) in tnames" :key="tname"
            :style="{
              background: tcolor[i],
            }"
            class="pick">
        </div>
    </div>
</template>

<script>
export default {
  name: 'ColorFrom',
  props: {
    names: Array,
    colors: Function,
    pos: Object,
  },
  data() {
    return {
    };
  },
  computed: {
    tcolors() {
      const c = this.names.map((_, i) => this.colors[i]);
      return [this.colors(-1), this.colors(-2)].concat(c);
    },
    tnames() {
      return ['未', '無'].concat(this.names);
    },
  },
};
</script>

<style scoped>

</style>
