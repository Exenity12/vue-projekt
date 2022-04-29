<template>
  <div>
      <h2>Home</h2>

      <a href="/items">Items</a>
  </div>
</template>


<script>
import appHeader from "@/components/appHeader"

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

