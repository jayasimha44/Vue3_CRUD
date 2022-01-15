<template>
  <form @submit.prevent="submitHandler">
    <h4>New Voter</h4>
    <div>
      <label>Name: </label>
      <input type="text" placeholder="Name" v-model="enteredName" />
    </div>
    <br />
    <div>
      <label>Age: </label>
      <input type="number" placeholder="Age" v-model="enteredAge" />
    </div>
    <br />
    <div>
      <button>Add Voter</button>
    </div>
  </form>
</template>

<script>
export default {
  emits: [],
  data() {
    return {
      enteredName: "",
      enteredAge: "",
    };
  },
  methods: {
    submitHandler() {
      this.$emit("add-voter", this.enteredName, this.enteredAge);
      this.enteredName = "";
      this.enteredAge = "";
    },
  },
};
</script>

<style></style>
