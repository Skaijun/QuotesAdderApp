<template>
  <div class="quote">
    <slot></slot>
  </div>
</template>

<script>
</script>

<style scoped>
.quote {
  background-color: aquamarine;
  padding: 10px 20px;
  width: 27%;
  margin: 10px 0;
  border-radius: 15px;
  min-height: 140px;
  font-size: 24px;
  line-height: 28px;
  font-family: "Chelsea Market", cursive;
  cursor: pointer;
  transition: all 0.5s ease-in-out;
  overflow-x: clip;
  overflow-wrap: break-word;
}
.quote:hover {
  background-color: bisque;
}
@media (max-width: 1000px) {
  .quote {
    width: 44%;
  }
}
@media (max-width: 840px) {
  .quote {
    width: 95%;
  }
}
</style>

