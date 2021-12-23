<template>
  <div>
    <div>
      <h3>Post method API</h3>
      <label>Name</label>
      <input type="text" name="name" v-model="name" />
      <br />
      <label>Email</label>
      <input type="text" name="email" v-model="email" />
      <br /><br />
      <button type="submit" @click="addUser">Add New user</button>
      <br />
      <button type="submit" @click="getUser">Get user Data</button>
    </div>
    <br /><br /><br />
    <div>
      <table>
        <tr>
          <th>Id</th>
          <th>Name</th>
          <th>Email</th>
        </tr>
        <tr v-for="user in users" :key="user.id">
          <td>{{ user.id }}</td>
          <td>{{ user.name }}</td>
          <td>{{ user.email }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "Login",
  data() {
    return {
      users: [],
      name: "",
      email: "",
    };
  },
  methods: {
    getUser() {
      axios
        .get("https://61bb1459e943920017784c3c.mockapi.io/crud")
        .then((res) => {
          this.users = res.data;
          console.log(res.data);
        })
        .catch((err) => console.log(err));
    },

    addUser() {
      axios
        .post("https://61bb1459e943920017784c3c.mockapi.io/crud", {
          name: this.name,
          email: this.email,
        })
        .then((res) => console.log(res))
        .catch((err) => console.log(err));
    },
  },
};
</script>