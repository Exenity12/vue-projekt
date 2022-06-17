<template>
    <form v-on:submit.prevent="onSubmit">
        <input type="text" v-model="title">
        <button type="submit">Create</button>
    </form>
</template>


<script>
export default {
    data(){
        return {
            title: ""
        }
    },
    methods: {
        onSubmit() {
            console.log("submit", this.title);
            if(this.title.trim()){
                const newItem = {
                    id: Date.now(),
                    title: this.title,
                    compledet: false,
                }
                this.$emit("add-item", newItem);
                this.title = "";
            }
        },
    },
}
</script>

<style scoped>

  form {
      display: flex;
  }

</style>