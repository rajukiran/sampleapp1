<template>
  <div class="record">
    <h1 v-if="employeeData.data">Welcome to {{ employeeData.data ? employeeData.data.employee_name : "" }}</h1>
    <div class="card">
      <div class="container">
        <h4><b>{{ employeeData.data ? employeeData.data.employee_name : "" }}</b></h4> 
        <p>{{ employeeData.data ? employeeData.data.description : "" }}</p> 
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Record',
  data() {
    return {
      employeeData: {}
    }
  },
  computed: {},
  mounted() {
    const that = this;
    this.$nextTick(() => {
      fetch("/data/employee.json")
        .then(res => res.json())
        .then(res => that.employeeData = res);
      // this.$alert("Hello Vue Simple Alert.");
    })
  }
}
</script>
<style lang="css" scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  width: 20%;
  margin: auto;
  border-radius: 5px;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

img {
  border-radius: 5px 5px 0 0;
}

.container {
  padding: 2px 16px;
}
</style>