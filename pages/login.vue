<template>
  <div class="hold-transition login-page">
    <div class="login-box">
      <div class="login-logo">
        <a href="../../index2.html"><b>Admin</b>LTE</a>
      </div>
      <!-- /.login-logo -->
      <div class="card">
        <div class="card-body login-card-body">
          <p class="login-box-msg">Sign in to start your session</p>

          <div class="input-group mb-3">
            <input
              type="text"
              class="form-control"
              placeholder="Username"
              v-model="username"
            />
            <div class="input-group-append">
              <div class="input-group-text">
                <span class="fas fa-user"></span>
              </div>
            </div>
          </div>
          <div class="input-group mb-3">
            <input
              type="password"
              class="form-control"
              placeholder="Password"
              v-model="password"
            />
            <div class="input-group-append">
              <div class="input-group-text">
                <span class="fas fa-lock"></span>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-8">
              <div class="icheck-primary">
                <input type="checkbox" id="remember" />
                <label for="remember">
                  Remember Me
                </label>
              </div>
            </div>
            <!-- /.col -->
            <div class="col-4">
              <button
                type="submit"
                class="btn btn-primary btn-block"
                @click="login"
                v-if="!loading"
              >
                Sign In
              </button>
              <button
                type="submit"
                class="btn btn-primary btn-block"
                @click="login"
                :loading="loading"
                v-else
              >
                <div class="spinner-border" role="status">
                  <span class="sr-only">Loading...</span>
                </div>
              </button>
            </div>
            <!-- /.col -->
          </div>

          <p class="mb-1">
            <NuxtLink to="/forgot-password">I forgot my password</NuxtLink>
          </p>

          <p class="mb-0">
            <NuxtLink to="/register" class="text-center"
              >Register a new membership</NuxtLink
            >
          </p>
        </div>
        <!-- /.login-card-body -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
      loading: false
    };
  },
  methods: {
    login() {
      this.loading = true;
      setTimeout(() => {
        if (this.username === "admin" && this.password === "admin") {
          this.$router.push("/dashboard");
        } else {
          this.loading = false;
        }
      }, 1000);
    }
  }
};
</script>

<style scoped>
.login-box {
  display: flex;
  flex-direction: column;
}
.btn-login {
  display: flex;
  flex-direction: row;
  align-items: center;
}
</style>
