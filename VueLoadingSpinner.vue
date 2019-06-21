<template>
  <div class="vue-spinner">
    <div
      class="vue-lds-ring"
      :style="{
        width: size ? size + 1 + 'rem' : '',
        height: size ? size + 1 + 'rem' : ''
      }"
    >
      <div
        v-for="i in 4"
        :key="i"
        :style="{
          'border-width': weight ? weight + 'rem' : '',
          'border-top-color': color ? color : '#40bbf4',
          width: size ? size + 'rem' : '',
          height: size ? size + 'rem' : '',
          'animation-timing-function': timing ? timing : ''
        }"
      ></div>
    </div>
    <p
      v-if="!noText"
      class="vue-spinner-block-text"
      :style="{ 'font-size': size / 3.3 + 'rem' }"
    >
      <slot>Loading</slot>
    </p>
  </div>
</template>

<script>
export default {
  props: {
    weight: {
      type: Number,
      default: 0.5
    },
    size: {
      type: Number,
      default: 5
    },
    color: {
      type: String,
      default: "black"
    },
    noText: {
      type: Boolean,
      default: true
    },
    timing: {
      type: String
    }
  }
};
</script>


<style scoped>
.vue-lds-ring {
  width: 7rem;
  height: 7rem;
  margin: 0 auto;
  display: flex;
}

.vue-lds-ring div {
  box-sizing: border-box;
  position: absolute;
  margin: 0.5rem;
  border: 0.5rem solid;
  border-radius: 50%;
  animation: vue-spinner-lds-ring 1s cubic-bezier(0.47, 0.32, 0.71, 0.37)
    infinite;
  border-color: transparent;
}
.vue-lds-ring div:nth-child(1) {
  animation-delay: -0.3s;
}
.vue-lds-ring div:nth-child(2) {
  animation-delay: -0.2s;
}
.vue-lds-ring div:nth-child(3) {
  animation-delay: -0.1s;
}

.vue-spinner .vue-spinner-block-text {
  font-weight: lighter;
  text-align: center;
  padding: 0 !important;
  margin: 0 !important;
}

@keyframes vue-spinner-lds-ring {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>

