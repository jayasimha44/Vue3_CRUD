<template>
  <li @click="$emit('delete', id)">{{ name }} <br />{{ age }}</li>
</template>

<script>
export default {
  props: {
    id: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
  },
  emits: ["delete"],
  data() {
    return {};
  },
  methods: {},
};
</script>

<style></style>
