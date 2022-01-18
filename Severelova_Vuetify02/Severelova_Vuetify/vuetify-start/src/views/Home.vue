<template>
  <div class="home">
    <EmployeeView :employees="employees" @delete="delEmpl" />
  </div>
</template>

<script>
// @ is an alias to /src
import EmployeeView from "@/components/EmployeeView.vue";
import axios from "axios"; // you may have to add that

export default {
  name: "Home",
  async created() {
    let result = await axios.get("http://localhost:3000/employees");
    this.employees = result.data;
  },
  data() {
    return {
      employees: [],
    };
  },
  components: {
    EmployeeView,
  },
  methods: {
    delEmpl(empl) {
      this.employees = this.employees.filter((elm) => elm != empl);
    },
  },
};
</script>
