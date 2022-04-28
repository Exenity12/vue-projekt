<template>
  <div>
    <ul>
      <appHeader
        v-for="head in header"
        v-bind:headitem="head" :key="head"
      />
    </ul>
  </div>
</template>


<script>
import appHeader from "@/components/appHeader"

export default {
  props:['header'],
  components: {
    appHeader
  }
}
</script>


<style scoped>
 ul {
   list-style: none;
   margin: 0;
   padding: 0;
}
</style>