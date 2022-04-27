<template>
  <button type="button" class="btn cube cube-hover">
    <a target="_" :href="$props.link">
      <div class="bg-top">
        <div class="bg-inner"></div>
      </div>
      <div class="bg-right">
        <div class="bg-inner"></div>
      </div>
      <div class="bg">
        <div class="bg-inner"></div>
      </div>
      <div class="text">{{ this.$props.title }}</div>
    </a>
  </button>
</template>

<script>
export default {
  setup() {},
  props: {
    link: {
      type: String,
    },
    title: {
      type: String,
    },
  },
};
</script>

<style scoped>

:root {
  --primary: #172a3a;
  --secondary: #141414;
  --tersier: #fca311;
}
.btn {
  display: block;
  padding: 0.7em 1em;
  background: transparent;
  outline: none;
  border: 0;
  color: #fca311;
  letter-spacing: 0.1em;
  font-family: monospace;
  font-size: 17px;
  font-weight: bold;
  z-index: 1;
}

.cube {
  position: relative;
  transition: all 0.5s;
}

.cube .bg-top {
  position: absolute;
  height: 10px;
  background: #fca311;
  bottom: 100%;
  left: 5px;
  right: -5px;
  transform: skew(-45deg, 0);
  margin: 0;
  transition: all 0.4s;
}

.cube .bg-top .bg-inner {
  bottom: 0;
}

.cube .bg {
  position: absolute;
  left: 0;
  bottom: 0;
  top: 0;
  right: 0;
  background: #fca311;
  transition: all 0.4s;
}

.cube .bg-right {
  position: absolute;
  background: #fca311;
  top: -5px;
  z-index: 0;
  bottom: 5px;
  width: 10px;
  left: 100%;
  transform: skew(0, -45deg);
  transition: all 0.4s;
}

.cube .bg-right .bg-inner {
  left: 0;
}

.cube .bg-inner {
  background: #141414;
  position: absolute;
  left: 2px;
  right: 2px;
  top: 2px;
  bottom: 2px;
}

.cube .text {
  position: relative;
  transition: all 0.4s;
}

.cube:hover .bg-inner {
  background: #fca311;
  transition: all 0.4s;
}

.cube:hover .text {
  color: #28282d;
  transition: all 0.4s;
}

.cube:hover .bg-right,
.cube:hover .bg,
.cube:hover .bg-top {
  background: #141414;
}

.cube:active {
  z-index: 9999;
  animation: bounce 0.1s linear;
}

@keyframes bounce {
  50% {
    transform: scale(0.9);
  }
}
</style>
