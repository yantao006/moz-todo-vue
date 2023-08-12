<script>
export default {
  name: "ToDoForm.vue",
  methods: {
    onSubmit() {
      if (this.label === "") {
        return;
      }
      this.$emit("todo-added", this.label);
      this.label = "";
      // console.log("label value:", this.label);
    }
  },
  data() {
    return {
      label: "",
    }
  }
}
</script>

<template>
  <form @submit.prevent="onSubmit">
    <h2 class="label-wrapper">
      <label for="new-todo-input" class="label_lg">
        What needs to be done?
      </label>
    </h2>
    <input
        type="text"
        id="new-todo-input"
        name="new-todo"
        autocomplete="off"
        v-model.trim.lazy="label"
        class="input__lg"
    />
    <button type="submit" class="btn btn__primary btn__lg">Add</button>
<!--    <button type="submit">Add</button>-->
  </form>
</template>

<style scoped>

</style>