<template>
  <div>
    <addNewItem
      v-on:add-item="addItem"
    />
    <appWindow
      v-bind:header="header"
      v-on:remove-item="removeItem"
    />
  </div>
</template>



<script>
import appWindow from "@/components/appWindow"
import addNewItem from "@/components/addNewItem"

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
    }
  },
}
</script>