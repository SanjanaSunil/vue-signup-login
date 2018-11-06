<template>

  <div class="login">

    <div class="row">
      <div class="col"></div>

        <div class="col"><div class="card outer"><div class="card-body text-center"><p class="card-text" style="font-size:20px;"><b>{{ heading }}</b></p></div><div class="card">
          <div class="card-body text-center">
            <div class="card inner"><div class="card-body text-center">
              <form>
                <div class="form-group">
                  <label for="inputsm">Email</label>
                  <input class="form-control input-sm" id="inputsm" type="text" style="color:white;" placeholder="Enter email">
                </div>
                <div class="form-group">
                  <label for="inputsm">Password</label>
                  <input class="form-control" id="inputsm" type="password" style="color:white;" placeholder="Enter password">
                </div>
              </form> 
            </div></div>
          </div>
          <p class="card-text"><input type="checkbox" value=""> Remember Me</p><br> 
          <button v-on:click="enter" class="btn btn-success"><b>LOGIN</b></button>
        </div></div></div>

      <div class="col"></div>
    </div> 

  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      heading: 'SIGN IN'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

/* @import '../../node_modules/bootstrap/dist/css/bootstrap.css'; */

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
</style>
