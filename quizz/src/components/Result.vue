<script>
export default {
  name: "Result",
  props: ["totalPoints"],
};
</script>

<template>
  <div class="result">
    <div class="title">You got sample result {{ totalPoints }}!</div>
    <div class="desc">Enter a short description here about the result.</div>
  </div>
</template>

<style lang="scss" scoped></style>
