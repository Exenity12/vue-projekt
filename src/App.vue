<template>
  <div id="app">
    <appWindow
      v-bind:header="header"
    />
  </div>
</template>

<script>
import appWindow from "@/components/appWindow"

export default {
  name: 'App',
  data(){
    return {
      header: [
        {id: 1, title: 'первый', completed: false},
        {id: 2, title: 'Bторой', completed: true},
        {id: 3, title: 'третий', completed: false},
      ]
    }
  },
  components: {
    appWindow
  }
}
</script>

<style>
</style>
