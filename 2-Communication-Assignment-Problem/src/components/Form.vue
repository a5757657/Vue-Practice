<template lang="">
  <div id="container">
    <h1>Add Friends</h1>
    <div id="formContainer">
      <form @submit.prevent="add">
        <div>
          <label for="name">name</label>
          <input v-model="name" id="name" name="name" type="text" />
        </div>
        <div>
          <label for="age">age</label>
          <input v-model="age" id="age" name="age" type="number" />
        </div>
        <div>
          <label for="phone">phone</label>
          <input v-model="phone" id="phone" name="phone" type="text" />
        </div>
        <div id="btn">
          <button :disabled='verify' >Add</button>
        </div>
      </form>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return{
      name: '',
      age: '',
      phone: ''
    }
  },
  methods: {
    add() {
      const data = {
        name: this.name,
        age: this.age,
        phone: this.phone,
        verify: true
      }
      this.$emit("addFriend", data);
    },
  },
  computed: {
    verify() {
      return !(this.name && this.age && this.phone)
    }
  }
};
</script>
<style lang=""></style>
