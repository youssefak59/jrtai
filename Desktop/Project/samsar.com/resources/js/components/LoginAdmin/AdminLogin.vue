<template>
  <div class="container-fluid px-1 px-md-5 px-lg-1 px-xl-5 py-5 mx-auto">
    <div class="card card0 border-0">
        <div class="row">
              <img src="https://i.imgur.com/CXQmsmF.png" class="logo">
            </div>
      <div class="row d-flex">
        <div class="col-lg-6">
          <div class="card1 pb-5">
            
            <div class="row px-3 justify-content-center mt-4 mb-5 border-line">
              <img src="https://i.imgur.com/uNGdWHi.png" class="image">
            </div>
          </div>
        </div>
        <div class="col-lg-6">
          <div class="card2 card border-0 px-4 py-5">
            <div class="row px-3">
              <label class="mb-1">
                <h6 class="mb-0 text-sm">Email Address</h6>
              </label>
              <input
                class="mb-4"
                type="text"
               v-model="AdminLogin.email"
                placeholder="Enter a valid email address"
              >
            </div>
            <div class="row px-3">
              <label class="mb-1">
                <h6 class="mb-0 text-sm">Password</h6>
              </label>
              <input type="password" v-model="AdminLogin.password" placeholder="Enter password">
            </div>
            <div class="row px-3 mb-4">
              <div class="custom-control custom-checkbox custom-control-inline">
                <input id="chk1" type="checkbox" name="chk" class="custom-control-input">
                <label for="chk1" class="custom-control-label text-sm">Remember me</label>
              </div>
              <a href="#" class="ml-auto mb-0 text-sm">Forgot Password?</a>
            </div>
            <div class="row mb-3 px-3">
              <button type="button" @click="LoginAdmin" class="btn btn-primary">Login</button>
            </div>
            
            </div>
          </div>
        </div>
      </div>
      <div class="bg-blue py-4">
        <div class="row px-3">
          <small class="ml-4 ml-sm-5 mb-2">Copyright &copy; 2021. All rights reserved.</small>
          <div class="social-contact ml-4 ml-sm-auto">
            <span class="fa fa-facebook mr-4 text-sm"></span>
            <span class="fa fa-google-plus mr-4 text-sm"></span>
            <span class="fa fa-linkedin mr-4 text-sm"></span>
            <span class="fa fa-twitter mr-4 mr-sm-5 text-sm"></span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
        AdminLogin: {
            email: "youssef@gmail.com",
            password: "123456"
        }
        }
    },
    methods: {
        LoginAdmin() {
            axios
                .post("/api/loginadmin", this.AdminLogin)
                .then(response => {
                  if (response.data == "admin") {
                    // localStorage.setItem("token", response.data["token"]);
                    window.location.href = "/dash#/fr/cms";
                    // alert("hello");
                    // alert("sadasdas");
                    // this.RedirectDash();
                  }
                }).catch(err=>{
                
                });
        }
    }
};
</script>
