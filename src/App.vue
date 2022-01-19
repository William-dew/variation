<template>
  <el-card class="box-card">
    <Variation />
  </el-card>
</template>

<script>
import Variation from "./components/Variation.vue";
export default {
  components: {
    Variation,
  },
};
</script>

<style lang="scss">
.el-card {
  width: 300px;
  &__body {
    text-align: center;
  }
}
</style>