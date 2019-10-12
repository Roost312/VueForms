<template>
  <div class="container">
    <form class="form-horizontal" v-if="!submitted">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <h1>File a Complaint</h1>
          <hr>
          <!-- Part 1 5 Points-->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->
          <app-name v-model="userData.userName"></app-name>

          <div class="form-group">
            <label for="email">Mail</label>
            <input class="form-control" v-model="userData.email" type="text" placeholder="email">
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input class="form-control" v-model="userData.password" type="text" placeholder="password">
          </div>
          <div class="form-group">
              <label for="storage" id="storage">Store Data? Yes/No</label>
              <label for="yes">
                <input v-model="userData.yesNo" type="radio" id="yes" value="yes"> Yes
              </label>
              <label for="no">
                <input v-model="userData.yesNo" type="radio" id="no" value="no"> No
              </label>
          </div>
          <div class="form-group text-right">
              <button class="btn-primary" @click="submit">Sumbit Form</button>
          </div>
          <!-- Part 2 5 Points -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->

          <!-- Part 3 5 Points -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
        </div>
      </div>
    </form>
    <hr>
    <div class="row" v-if="submitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ userData.userName }}</p>
            <p>Mail: {{ userData.email }}</p>
            <p>Password: {{ userData.password }}</p>
            <p>Store in Database?: {{ userData.yesNo }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Name from './Name.vue';

  export default {
    data () {
      return {
        userData: {
          userName: '',
          email: '',
          password: '',
          yesNo: 'yes'
        },
        submitted: false
      }
    },
    methods: {
      submit () {
        this.submitted = true
      }
    },
    components: {
      appName: Name
    }
  }
</script>

<style>
.row {
  background-color: rgba(0, 0, 0, 0.1);
  padding: 20px;
}

.form-group {
  padding: 10px;
}

#storage {
  padding-right: 4%;
}

</style>