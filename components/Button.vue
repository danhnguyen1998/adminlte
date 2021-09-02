<template>
  <button
    type="button"
    class="btn btn-primary btn-block"
    @click="click"
    v-if="!loading"
  >
    {{ name }}
  </button>
  <button type="button" class="btn btn-primary btn-block" v-else>
    <div class="spinner-border" role="status">
      <span class="sr-only">Loading...</span>
    </div>
  </button>
</template>

<script>
export default {
  props: {
    loading: Boolean,
    name: String,
    onClick: Function
  },
  methods: {
    click() {
      this.onClick();
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
