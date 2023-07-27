<template>
  <div class="card card-w70">
    <component
      v-for="block in blocks"
      :key="block.id"
      :is="'app-' + block.value"
      :url="block.text"
      >{{ block.text }}</component
    >
    <h3 v-if="blocks.length === 0">
      Добавьте первый блок, чтобы увидеть результат
    </h3>
  </div>
</template>

<script>
import AppText from '@/components/AppText.vue';
import AppSubtitle from '@/components/AppSubtitle.vue';
import AppAvatar from '@/components/AppAvatar.vue';
import AppTitle from '@/components/AppTitle.vue';
export default {
  props: ['blocks'],
  components: {
    AppText,
    AppSubtitle,
    AppAvatar,
    AppTitle,
  },
};
</script>

<style lang="scss" scoped></style>
