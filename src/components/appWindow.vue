<template>
  <div>
    <ul>
      <appHeader
        v-for="(head, index) in header"
        v-bind:indexitem="index"
        v-bind:headitem="head" :key="head"
        v-on:remove-item="removeItem"
      />
    </ul>
  </div>
</template>


<script>
import appHeader from "./AppHeader"

export default {
  props:['header'],
  components: {
    appHeader
  },
  methods: {
    removeItem(id) {
      this.$emit("remove-item", id);
    },
  },
}
</script>

<style scoped>
 ul {
   list-style: none;
   margin: 0;
   padding: 0;
}
</style>