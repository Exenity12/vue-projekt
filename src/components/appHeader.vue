<template>
  <div>
    <li>
      <span v-bind:class="{done: headitemLocal.completed}">
        <input type="checkbox" 
        v-on:change="markCompleted">
        <strong>{{indexitem + 1}}</strong>
        {{headitemLocal.title}}
      </span>
      <button v-on:click="$emit('remove-item', headitemLocal.id)">&times;</button>
    </li>
  </div>
</template>
    
<script>
export default {
  props: ['headitem', 'indexitem'],
  data() {
    return {
      headitemLocal: this.headitem,
    };
  },
  methods: {
    markCompleted() {
      this.headitemLocal.completed = !this.headitemLocal.completed
    },
  },
}
</script>

<style scoped>
 li {
   border: 1px solid grey;
   display: flex;
   justify-content: space-between;
   padding: 2px;
   margin: 2px;
}

 button{
   background: red;
   color: black;
   font-weight: bold;
 }

  .done{
    text-decoration: line-through;
  }

</style>