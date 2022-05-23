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
      console.log("Hi Vue")
    }
  }
}
</script>


<style>

</style>