<template>
  <v-card>
    <v-img
      :src="employee.picture.large | path"
      max-width="200"
      class="white--text align-end ma-3"
      alt="picture of employee"
      align="center"
    >
      <v-card-title class="align-end fill-height empl-name"
        >{{ employee.name.title }} {{ employee.name.first }}
        {{ employee.name.last }}</v-card-title
      >
    </v-img>
    <v-card-text class="text--primary">
      <div>
        <label class="d-none d-md-inline font-weight-bold">Email:</label>
        {{ employee.email }} <br />
        <label class="d-none d-md-inline font-weight-bold">Phone:</label>
        {{ employee.phone }}
      </div>
    </v-card-text>

    <v-card-actions>
      <v-btn depressed @click="$emit('delete', employee)"
        ><span>Delete </span><v-icon>mdi-delete</v-icon></v-btn
      >
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: {
    employee: Object,
  },
  filters: {
    path: function (filename) {
      return "http://localhost:3000/" + filename;
    },
  },
};
</script>

<style lang="scss" scoped>
.empl-name {
  text-shadow: 3px 3px black;
}
</style>