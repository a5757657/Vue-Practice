<template lang="">
  <section>
    <form-page
      @addFriend="handleAddFriend"
    ></form-page>
    <card
      v-for="(friend, index) in friends"
      :key="index"
      :friend='friend'
      :index='index'
      @delFriend="handleDelFriend"
    ></card>
  </section>
</template>
<script>
export default {
  data() {
    return {
      friends: [],
    };
  },
  methods: {
    handleAddFriend(data) {
      this.friends.push(data)
    },
    handleDelFriend(index) {
      console.log(index)
      this.friends.splice(index, 1)
    }
  }
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: white;
  font-weight: bold;
  font-family: "Bebas Neue", cursive;
  letter-spacing: 5px;
}

section {
  margin: 0px auto;
  display: flex;
  width: fit-content;
  justify-content: center;
  flex-direction: column;
  padding: 40px;
  gap: 40px;
}
#container {
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 5px 11px -5px black;
  background-color: cornflowerblue;
  display: flex;
  flex-direction: column;
  align-items: center;
}
h1,
h2 {
  text-align: center;
}
#formContainer {
  margin-top: 20px;
}
form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
form > div {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  flex-wrap: wrap;
}
input {
  width: 200px;
  padding: 5px;
  color: black;
}
button {
  margin: 0px auto;
  margin-top: 20px;
  padding: 5px;
  color: black;
}
#btn {
  text-align: center;
}
</style>
