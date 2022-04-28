<template>
  <div>
    <li>
      <span v-bind:class="{done: headitem.completed}">
        <input type="checkbox" 
        v-on:change="markCompleted">
        <strong>{{headitem.id}}</strong>
        {{headitem.title}}
      </span>
      <button>&times;</button>
    </li>
  </div>
</template>

<script>
export default {
  props: ['headitem'],
  methods: {
        markCompleted() {
          this.headitem.completed = !this.headitem.completed
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