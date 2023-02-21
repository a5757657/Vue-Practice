<template lang="">
  <div id="container">
    <h2>{{ friend.name }}</h2>
    <div>age: {{ friend.age }}</div>
    <div>phone: 12</div>
    <button @click='del'>Delete</button>
  </div>
</template>
<script>
export default {
  props: ['friend', 'index'],
  methods: {
    del() {
      this.$emit('delFriend', this.index)
    }
  }
};
</script>
<style lang=""></style>
