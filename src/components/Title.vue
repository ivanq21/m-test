<template>
    <h1 class="title">{{ msg }}</h1>
</template>

<script>
export default {
  name: 'Title',
  props: {
    msg: String
  }
}
</script>

<style scoped lang="scss">
  .title {
      font-weight: bold;
      font-size: 32px;
      line-height: 40px;
      margin: 0 0 56px 0;
  }
</style>
