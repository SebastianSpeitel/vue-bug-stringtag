<template>
  <div />
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    obj: Object,
    obj2: { type: Object },
    obj3: { validator: o => typeof o === "object" }
  }
};
</script>
