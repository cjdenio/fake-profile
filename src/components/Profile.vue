<template>
  <div>
    <img class="avatar" :src="image" />
    <h1 class="name">{{ name }}</h1>
    <table class="fields">
      <tr>
        <td><i class="fas fa-briefcase"></i></td>
        <td>
          <div class="company field">
            {{ job }}, <b>{{ company }}</b>
          </div>
        </td>
      </tr>
      <tr>
        <td><i class="fas fa-envelope"></i></td>
        <td>
          <div class="email field">
            {{ email }}
          </div>
        </td>
      </tr>
      <tr>
        <td><i class="fas fa-user"></i></td>
        <td>
          <div class="bio field">
            {{ bio }}
          </div>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
import faker from "faker";

export default {
  name: "Profile",
  data() {
    return {
      firstName: "",
      lastName: "",
      email: "",
      image: "",
      job: "",
      company: "",
      bio: "",
    };
  },
  created() {
    this.firstName = faker.name.firstName();
    this.lastName = faker.name.lastName();
    this.email = faker.internet.email(this.firstName, this.lastName);
    this.image = faker.image.avatar();
    this.company = faker.company.companyName();
    this.job = faker.name.jobTitle();
    this.bio = faker.lorem.paragraph();
  },
  computed: {
    name() {
      return this.firstName + " " + this.lastName;
    },
  },
};
</script>

<style scoped>
.avatar {
  height: 200px;
  width: 200px;
  border-radius: 1000px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.3);
}

.name {
  font-size: 40px;
}

.has-icon > i {
  margin-right: 10px;
}
.field {
  font-weight: normal;
}
.fields {
  max-width: 500px;
  width: 100%;
  display: inline-block;
  text-align: center;
}

.fields td:first-child > i {
  margin-right: 10px;
}
.fields td:last-child {
  text-align: left;
}
.fields td {
  padding: 10px 0;
  vertical-align: top;
}
</style>
