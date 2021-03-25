<template>
  <div class="about">
    <h1>Welcome to User: {{ username }}</h1>
  </div>
</template>
<script>
import { mapState } from "vuex";
export default {
  computed: {
    ...mapState(["username"])
  }
}
</script>