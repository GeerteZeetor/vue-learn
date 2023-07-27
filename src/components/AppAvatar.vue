<template>
  <div class="avatar">
    <img :src="url" />
  </div>
</template>

<script>
export default {
  props: ['url'],
};
</script>

<style lang="scss" scoped>
.avatar {
  display: flex;
  justify-content: center;
  img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
}
</style>
