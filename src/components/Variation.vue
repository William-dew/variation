<template>
  <el-input-number
    v-model.number="startValue"
    placeholder="Initiale €"
    size="large"
    @input="calc"
    :suffix-icon="Calendar"
  />
  <el-input-number
    v-model.number="endValue"
    placeholder="Finale €"
    size="large"
    @input="calcVariation"
  />
  <el-input-number
    v-model.number="variation"
    placeholder="Variation %"
    size="large"
    @input="calcEndValue"
  />
</template>


<script>
export default {
  data() {
    return {
      startValue: undefined,
      endValue: undefined,
      variation: undefined,
    };
  },
  methods: {
    calcVariation() {
      console.log("calcul variation");
      this.variation = Number(
        (((this.endValue - this.startValue) / this.startValue) * 100).toFixed(2)
      );
    },
    calcEndValue() {
      this.endValue = Number(
        (this.startValue * (1 + this.variation / 100)).toFixed(2)
      );
    },
    calc() {
      this.calcVariation();
    },
  },
};
</script>

<style>
.el-input-number {
  margin: 0.25rem;
}
</style>
