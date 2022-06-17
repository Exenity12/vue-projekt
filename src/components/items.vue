<template>
  <div>
    <addNewItem
        v-on:add-item="addItem"
    />
    <appWindow
        v-bind:header="header"
        v-on:remove-item="removeItem"
        v-if='header.length'
    />
    <div v-else>No array</div>
  </div>
</template>



<script>
import appWindow from "./AppWindow"
import addNewItem from './AppNewItem'

export default {
  name: 'App',
  data(){
    return {
      header: [
        {id: 1, title: 'первый', completed: false},
        {id: 2, title: 'Bторой', completed: false},
        {id: 3, title: 'третий', completed: false},
      ]
    }
  },
  components: {
    appWindow, addNewItem
  },
  methods: {
    removeItem(id) {
      this.header = this.header.filter(t => t.id !== id)
    },
    addItem(item){
      this.header.push(item);
      console.log(this.header);
    }
  },
}
</script>