<template>
  <div>
    <Comp :obj="obj" :obj2="obj" :obj3="obj" />
  </div>
</template>

<script>
import Comp from "./components/Component.vue";

export default {
  components: {
    Comp
  },
  setup() {
    const obj = {
      get [Symbol.toStringTag]() {
        return "NotObject";
      }
    };

    return { obj };
  }
};
</script>
