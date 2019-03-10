<template>
  <div class>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Add Todo..">
      <input type="submit" value="Submit" class="btn">
    </form>
  </div>
</template>

<script>
// import uuid from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  props: [],
  data() {
    return {};
  },
  computed: {},
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      };
      //send up to parent
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  },
  components: {}
};
</script>
<style>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
input[type="submit"] {
  flex: 2;
}
</style>
