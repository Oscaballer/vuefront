<template>
  <section>
    <vf-m-row :no-gutters="noGutters">
      <vf-m-col
        sm="12"
        :md="list || column? 12: 12 / gridSize"
        v-for="(value, index) in products"
        :key="index"
      >
        <vf-o-product-thumb :product="value" :wide="list" />
      </vf-m-col>
    </vf-m-row>
  </section>
</template>
<script>
export default {
  props: {
    products: {
      type: Array,
      default: []
    },
    column: {
      type: Boolean,
      default: false
    },
    list: {
      type: Boolean,
      default: false
    },
    noGutters: {
      type: Boolean,
      default() {
        return this.$vuefront.options.productGridNoGutters
      }
    },
    gridSize: {
      type: Number,
      default() {
        return this.$vuefront.options.productGridSize
      }
    }
  }
};
</script>
