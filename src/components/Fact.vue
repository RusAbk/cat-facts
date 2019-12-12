<template>
  <div class="fact" v-on:click="$emit('update')">
    <h2>Интересный факт</h2>
    <img src="../assets/kitty.png" alt="" />
    <p>
      <slot></slot>
    </p>
  </div>
</template>

<script>
export default {
  name: "Fact"
};
</script>

<style>
.fact {
  width: 300px;
  border-radius: 10px;
  padding: 20px;
  font-family: "Arial", sans-serif;
  box-shadow: 0px 0px 10px 0px rgba(50, 50, 50, 0.5);
  background-color: rgb(238, 248, 237);
  text-align: center;
  color: #3b4668;
  cursor: pointer;
  transition: 0.3s;
}
.fact:hover {
  transform: scale(1.05);
  box-shadow: 0px 0px 13px 0px rgba(50, 50, 50, 0.5);
}
.fact h2 {
  font-size: 22px;
  font-weight: 900;
}
.fact h2:after {
  content: " ";
  display: block;
  width: 50px;
  height: 3px;
  background-color: #3b4668;
  margin: 15px auto;
}
.fact p {
  font-size: 16px;
  color: #848aa0;
}
</style>
