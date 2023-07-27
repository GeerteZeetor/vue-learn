<template>
  <div class="container column">
    <app-form @submit="addBlock"></app-form>
    <app-view :blocks="blocks"></app-view>
  </div>
  <app-comment-block></app-comment-block>
</template>

<script>
import AppView from '@/components/AppView.vue';
import AppForm from '@/components/AppForm.vue';
import AppCommentBlock from '@/components/AppCommentBlock.vue';

export default {
  data() {
    return {
      blocks: [],
    };
  },
  methods: {
    addBlock(block) {
      this.blocks.push(block);
      console.log(this.blocks);
    },
  },
  computed: {},
  components: { AppForm, AppView, AppCommentBlock },
};
</script>

<style>
* {
  word-wrap: anywhere;
}
</style>
