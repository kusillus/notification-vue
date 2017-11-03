<template>
  <div class="notification-container">
    <div class="icon-box">
      <i v-if="status">
        <svg style="fill:#4CAF50;"xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" width="30" height="30" viewBox="0 0 24 24"><path d="M12,2A10,10 0 0,1 22,12A10,10 0 0,1 12,22A10,10 0 0,1 2,12A10,10 0 0,1 12,2M12,4A8,8 0 0,0 4,12A8,8 0 0,0 12,20A8,8 0 0,0 20,12A8,8 0 0,0 12,4M11,16.5L6.5,12L7.91,10.59L11,13.67L16.59,8.09L18,9.5L11,16.5Z" /></svg>
      </i>
      <i v-else>
        <svg style="fill:#ee6e73;" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" width="30" height="30" viewBox="0 0 24 24"><path d="M12,20C7.59,20 4,16.41 4,12C4,7.59 7.59,4 12,4C16.41,4 20,7.59 20,12C20,16.41 16.41,20 12,20M12,2C6.47,2 2,6.47 2,12C2,17.53 6.47,22 12,22C17.53,22 22,17.53 22,12C22,6.47 17.53,2 12,2M14.59,8L12,10.59L9.41,8L8,9.41L10.59,12L8,14.59L9.41,16L12,13.41L14.59,16L16,14.59L13.41,12L16,9.41L14.59,8Z" /></svg>
      </i>
    </div>
    <div class="notification-detail">
      <slot name="title"></slot>
      <slot name="description"></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ['status'],
  data () {
    return {
    }
  },
  methods: {
  }
}
</script>

<style lang="scss">
.notification-container{
  background-color: white;
  padding: .5rem .7rem;
  border-radius: .3rem;
  display: flex;
  box-shadow: 0 4px 5px 0 rgba(0,0,0,0.14),0 1px 10px 0 rgba(0,0,0,0.12),0 2px 4px -1px rgba(0,0,0,0.3);
  margin-bottom: 0.6rem;
  position: relative;
  animation-duration: 2s;
  animation-name: showHide;
  overflow: hidden;
}
@keyframes showHide {
  0% {
    right: -20.6rem;
    opacity: 0;
  }
  30%{
    right: 0;
    opacity: 1;
  }
  100%{
    right: 0;
    opacity: 1;
  }
}
.notification-detail{
  padding-left: .5rem;
  display: flex;
  flex-flow: row wrap;
  text-align: left;
  h5{
    width: 100%;
    margin: 0;
    color: #656565;
  }
  span{
    width: 100%;
    font-size: 12px;
    color: #909090;
  }
}
.icon-box{
  display: flex;
  align-items: center;
  i{
    display: flex;
  }
}
</style>
