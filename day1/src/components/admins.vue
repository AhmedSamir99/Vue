.name{ text-align: center; font-size: 32px; padding: 5px; font-family: 'Dancing
Script',monospace; } .bio{ text-align: center; width: 30%; margin: auto;
font-family: cursive; font-size: px; padding: 2%; } .albums{ margin-left: auto;
} .image-container { width:40%; margin: 20px auto; display: flex; flex-wrap:
wrap; justify-content: center; } .albums { width: 50%; height: 250px; margin:
0px; } .home{ text-align: center; font-size: 40px; margin-top: 3%; font-family:
'Dancing Script', sans-serif; border-radius: 4px; padding: 5px 10px;
text-decoration: underline; color: black; } .home span { cursor: pointer;
display: inline-block; position: relative; transition: 0.5s; } .home span:after
{ content: '\00bb'; position: absolute; opacity: 0; top: 0; right: -20px;
transition: 0.5s; } .home:hover span { padding: 0px 20px 0px 25px;
background-color: #B2A4FF; } .home:hover span:after { opacity: 1; right: 0; }
SAMAR — Today at 6:10 PM {% extends 'app2.html' %} {% block content %}
<h1>FROM APP</h1>
<h1>{{name}}</h1>
{% endblock content %} SAMAR — Today at 7:19 PM
<template>
  <div>
    <table class="container">
      <h2>Admins</h2>
      <tr>
        <th>Name</th>
        <th>Age</th>
        <th>Role</th>
      </tr>
      <tr v-for="admin in filterAdmins" :key="admin.name">
        <td>{{ admin.name }}</td>
        <td>{{ admin.age }}</td>
        <td>{{ admin.role }}</td>
        <button @click="deleteAdmin(admin)" class="delete">Delete</button>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "AdminPage",
  inject: ["roles"],
  computed: {
    filterAdmins() {
      return this.roles.filter((admin) => admin.role === "admin");
    },
  },
  methods: {
    deleteAdmin(admin) {
      const index = this.roles.findIndex((a) => a.name === admin.name);
      if (index !== -1) {
        this.roles.splice(index, 1);
      }
    },
  },
};
</script>

<style scoped></style>
