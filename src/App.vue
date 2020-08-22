<template>
  <div>
    <button @click="val += 1" v-text="'Click'" />
    <p v-for="(v, i) of iter" :key="i" v-text="v" />
  </div>
</template>

<script>
import { computed, ref, watch } from "vue";

function* gen(val) {
  yield val.value;
}

export default {
  setup() {
    const val = ref(1);
    const iter = computed(() => gen(val));

    watch(val, () => {
      console.log(iter.value);
    });

    return { val, iter };
  }
};
</script>
