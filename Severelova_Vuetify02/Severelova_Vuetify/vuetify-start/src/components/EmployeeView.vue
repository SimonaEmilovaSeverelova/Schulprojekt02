<template>
  <div class="v-container">
    <div class="row d-sm-flex">
      <EmployeeCard
        class="col-md-3 col-sm-6 col-xs-6 pa-1 pa-sm-2"
        v-for="empl of employees"
        :key="empl.id"
        :employee="empl"
        @delete="$emit('delete', empl)"
      />
    </div>
  </div>
</template>

<script>
import EmployeeCard from "@/components/EmployeeCard";

export default {
  components: {
    EmployeeCard,
  },
  props: {
    employees: Array,
  },
};
</script>

<style lang="scss" scoped>
</style>