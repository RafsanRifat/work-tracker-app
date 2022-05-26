<template>
  <button :style="{background: color}" class="btn" @click="onClick">{{ text }}</button>
</template>


<script>
export default {
  name: 'Button_tracker',
  props: {
    text: String,
    color: String
  },
  methods: {
    onClick() {
      this.$emit('btn-click')
    }
  }
}
</script>


<style>

</style>