<template>
  <section>
    <h1>Voters List</h1>
    <user-data @add-voter="addVoter"></user-data>
    <ul>
      <active-user
        v-for="voter in voters"
        :key="voter.id"
        :id="voter.id"
        :name="voter.name"
        :age="voter.age"
        @delete="deleteVoter"
      ></active-user>
    </ul>
  </section>
</template>

<script>
import ActiveUser from "./components/ActiveUser.vue";
import UserData from "./components/UserData.vue";

export default {
  components: { ActiveUser, UserData },
  data() {
    return {
      voters: [
        {
          id: 1,
          name: "jayasimha",
          age: 26,
        },
        {
          id: 2,
          name: "Sainath",
          age: 26,
        },
        {
          id: 3,
          name: "Vishnu",
          age: 28,
        },
      ],
    };
  },
  methods: {
    addVoter(name, age) {
      const newVoter = {
        id: new Date().toISOString(),
        name: name,
        age: age,
      };
      this.voters.push(newVoter);
    },
    deleteVoter(voterId) {
      this.voters = this.voters.filter((voter) => voter.id !== voterId);
    },
  },
};
</script>

<style>
* {
  width: 80%;
  margin: auto;
}
h1,
form {
  border: 1px solid grey;
  padding: 1rem;
  border-radius: 10px;
  background-color: rgb(50, 114, 50);
  color: white;
  text-align: center;
  margin: 2rem;
}
li {
  list-style: none;
  border: 1px solid grey;
  border-radius: 10px;
  margin: 5px 0;
  background-color: rgb(50, 114, 50);
  color: white;
  text-align: center;
  padding: 1rem;
  cursor: pointer;
}
input {
  padding: 0.5rem;
  border: none;
  border-radius: 20px;
}
button {
  padding: 0.5rem;
  background-color: salmon;
  color: white;
  font-size: 20px;
  border: none;
  border-radius: 20px;
  cursor: pointer;
}
</style>
