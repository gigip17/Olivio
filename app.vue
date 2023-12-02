<template>
  <div>
    <h1>
      <span style="color: violet">Ol</span>
      <span style="color: indigo">iv</span>
      <span style="color: blue">ie</span>
      <span style="color: green">r </span>
      <span style="color: yellow">es</span>
      <span style="color: orange">t </span>
      <span style="color: red">ho</span>
      <span style="color: violet">mo</span>
      <span style="color: indigo">se</span>
      <span style="color: blue">xu</span>
      <span style="color: green">el</span>
    </h1>
    <div id="heartContainer"></div>
  </div>
</template>

<script>
export default {
  mounted() {
    this.createHearts();
  },
  methods: {
    createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = Math.random() * 2 + 3 + 's'; // Random duration between 3s and 5s
      this.$el.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 5000); // Remove heart after 5 seconds
    },
    createHearts() {
      setInterval(() => {
        this.createHeart();
      }, 300); // Create a new heart every 300 milliseconds
    },
  },
};
</script>

<style>
.heart {
  width: 50px;
  height: 50px;
  position: absolute;
  background-color: red;
  animation: appearDisappear 2s infinite;
}

.heart:before,
.heart:after {
  content: '';
  width: 50px;
  height: 50px;
  background-color: red;
  border-radius: 50px;
  position: absolute;
  top: 0;
}

.heart:before {
  left: -25px;
}

.heart:after {
  top: -25px;
}
</style>
