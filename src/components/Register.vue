<template>
  <div class="register">

    <div class="row">
      <div class="col"></div>

        <div class="col"><div class="card outer"><div class="card-body text-center"><p class="card-text" style="font-size:20px;"><b>{{ heading }}</b></p></div><div class="card">
          <div class="card-body text-center">
            <div class="card inner"><div class="card-body text-center">
              <form @submit.prevent="signUp">
                <div class="form-group">
                  <label for="inputsm">Name</label>
                  <input v-validate="'required|alpha_spaces'" name="name" class="form-control input-sm" id="inputsm" type="text" style="color:white;" placeholder="Enter your name">
                  <p class="alert" v-if="errors.has('name')">{{ errors.first('name') }}</p>
                </div>
                <div class="form-group">
                  <label for="inputsm">Phone number</label>
                  <input v-validate="'required|regex:^6789[0-9]*$|digits:10'" name="phone" class="form-control input-sm" id="inputsm" type="text" style="color:white;" placeholder="Enter your phone number">
                  <p class="alert" v-if="errors.has('phone')">{{ errors.first('phone') }}</p>
                </div>
                <div class="form-group">
                  <label for="inputsm">Email</label>
                  <input v-validate="'required|email'" name="email" class="form-control input-sm" id="inputsm" type="text" style="color:white;" placeholder="Enter email">
                  <p class="alert" v-if="errors.has('email')">{{ errors.first('email') }}</p>
                </div>
                <div class="form-group">
                  <label for="inputsm">Create Password</label>
                  <input class="form-control" v-validate="'required|min:6|max:12|confirmed:pw_confirm'" name="password" id="inputsm" type="password" style="color:white;" placeholder="Enter password">
                  <p class="alert" v-if="errors.has('password')">{{ errors.first('password') }}</p>
                </div>
                <div class="form-group">
                  <label for="inputsm">Re-enter Password</label>
                  <input class="form-control" ref="pw_confirm" name="password_confirm" id="inputsm" type="password" style="color:white;" placeholder="Re-enter password">
                </div>
                <div class="form-group">
                  <label for="inputsm">Upload Image</label><br>
                  <input v-validate="'required|image|size:4096'" name="image" type="file">
                  <p class="alert" v-if="errors.has('image')">{{ errors.first('image') }}</p>
                </div>
              </form> 
            </div></div>
          </div>
          <button v-on:click="signUp" class="btn btn-success"><b>REGISTER</b></button>
        </div></div></div>

      <div class="col"></div>
    </div> 

  </div>
</template>

<script>
export default {
  name: 'Register',
  data() {
    return {
      heading: 'SIGN UP'
    }
  },
  methods : {
      signUp(){
          this.$validator.validateAll().then((result) => {
          if (result) {
            console.log('Valid');
          } else {
            console.log('Not valid');
          }
        })
      }
  }
}
</script>

<style scoped>

.card-text {
  color: white;
}

.card {
  background-color: #1d2b49;
}

.inner {
  background-color: #1e2a44;
}
.outer {
  background-color: #17233b;
}
#inputsm {
  background-color: #12192c;
}
.alert {
  color: red;
}

</style>
