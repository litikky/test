<template>
  <div class="toast" v-if="isShow">{{message}}</div>
</template>

<script>
export default {
  name: 'Toast',
  data() {
    return {
      message: '',
      isShow: false
    }
  },
  methods: {
    show(message='默认文本', duration=1500) {
      this.message = message
      this.isShow = true

      setTimeout(() => {
        this.message = ''
        this.isShow = false
      }, duration) 
    }
  }
}
</script>

<style scoped>
.toast {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 10px;
  background-color: rgba(0, 0, 0, .8);
  color: #fff;
  border-radius: 5px;
  z-index: 999;
}
</style>