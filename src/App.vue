<template>
  <div id="app" class="small-container">
    <img alt="Vue logo" src="./assets/logo.png">
    <hello-world msg="Welcome Willi to Your Vue.js App"/>
    <h1>Employees</h1>

    <employee-form  @add:employee="addEmployee"/>
    <employee-table :employees="employees" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import EmployeeTable from '@/components/EmployeeTable'
import EmployeeForm from './components/EmployeeForm'

export default {
  name: 'App',
  components: {
    HelloWorld,
    EmployeeTable,
    EmployeeForm
  },

  data() {
    return {
      employees: [
        {
          id: 1,
          name: 'Richard Hendricks',
          email: 'richard@piedpiper.com',
        },
        {
          id: 2,
          name: 'Bertram Gilfoyle',
          email: 'gilfoyle@piedpiper.com',
        },
        {
          id: 3,
          name: 'Dinesh Chugtai',
          email: 'dinesh@piedpiper.com',
        },
      ],
    }
  },

  methods: {
    addEmployee: function(employee) {
      console.log("addEmpoyee");
      this.employees = [...this.employees, employee]
    }
  }

}

</script>

<style>
</style>
