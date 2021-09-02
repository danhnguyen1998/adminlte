<template>
  <div class="loading">
    <div class="spinner-grow " role="status">
      <span class="sr-only">Loading...</span>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    this.$router.push("/login");
  }
};
</script>

<style scoped>
.loading {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}
</style>
