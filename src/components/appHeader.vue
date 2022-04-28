<template>
  <div>
    <li>
      <span v-bind:class="{done: headitemLocal.completed}">
        <input type="checkbox" 
        v-on:change="markCompleted">
        <strong>{{headitemLocal.id}}</strong>
        {{headitemLocal.title}}
      </span>
      <button>&times;</button>
    </li>
  </div>
</template>

<script>
export default {
  props: ['headitem'],
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