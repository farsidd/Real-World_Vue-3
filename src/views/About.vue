<template>
  <div class="about">
    <input @keyup="btn" v-model="msg">
  </div>
</template>
<script>


export default {
  data() {
    return {
      msg: ''
    }
  },
  methods: {
    btn() {
      console.log(this.msg)
    }
  }

}
</script>