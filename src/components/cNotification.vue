<template>

  <div class="notification-position">
      <card v-for="(el, idx) in notifyArray" :key="idx" :status="el.status">
        <h5 slot="title">{{el.title}}</h5>
        <span slot="description">{{el.description}}</span>
      </card>
  </div>

</template>

<script>
import card from './cCard.vue'
export default {
  props: ['notifyArray'],
  data () {
    return {
    }
  },
  methods: {

  },
  components: {
    card
  }
}
</script>

<style lang="scss">
.notification-position{
  position: absolute;
  bottom: 2rem;
  right: 0;
  overflow: hidden;
  padding-right: 1rem;
  padding-left: 1rem;
  width: 20rem;
  transition: all 2s;
}
</style>
