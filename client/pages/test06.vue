<template>
  <div>
    <h1>Name List</h1>
    <input type ="text" v-model="username">
    <input type ="email" v-model="email">
    <button @click="doAdd">Add Customer</button>
    <ul>
      <li v-for="c in customers" :key="c.id">
        <span>{{ c.id }}</span>
        <span>{{ c.username }}</span>
        <span>{{ c.email }}</span>
      </li>
    </ul>
    <br /><br />
    <!-- tbody>tr>td*3 || tbody>tr*5>td*3 -->
    <table>
      <thead>
        <tr>
          <td>Id</td>
          <td>Username</td>
          <td>Email</td>
        </tr>
      </thead>
      <tbody>
        <tr v-for="c in customers" :key="c.id">
          <td>{{ c.id }}</td>
          <td>{{ c.username }}</td>
          <td>{{ c.email }}</td>
        </tr>
      </tbody>
    </table>
    <br /><br />
    <ul>
      <li v-for="(c,index) in customers" :key="c.id">
        <span>{{ index }}</span>
        <span>{{ c.id }}</span>
        <span>{{ c.username }}</span>
        <span>{{ c.email }}</span>
      </li>
    </ul>
    <br /><br />
<ul>
      <li v-for="i in 10" :key="i">
        <span>{{ i }}</span>
      </li>
    </ul>
    <br /><br />
  </div>
</template>
<script>
export default {
  data() {
    return {
        username:'',
        email:'',
      customers: [
        { id: 1, username: "sunvodz1", email: "sunvo1@sunvo.sunvo" },
        { id: 2, username: "sunvodz2", email: "sunvo2@sunvo.sunvo" },
        { id: 3, username: "sunvodz3", email: "sunvo3@sunvo.sunvo" }
      ]
    };
  },
  methods: {
    doAdd() {
        let id = this.customers.length + 1
      this.customers.push({
        id: id,
        username: this.username,
        email: this.email+"@sunvo.sunvo"
      });
    }
  }
};
</script>
