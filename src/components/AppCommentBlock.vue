<template>
  <app-loader v-if="isLoading"></app-loader>
  <div v-else class="container">
    <p v-if="!comments.length">
      <button class="btn primary" @click="loadComments">
        Загрузить комментарии
      </button>
    </p>
    <app-comment-card :comments="comments" v-else></app-comment-card>
  </div>
</template>

<script>
import AppCommentCard from '@/components/AppCommentCard.vue';
import axios from 'axios';
import AppLoader from '@/components/AppLoader.vue';

export default {
  data() {
    return {
      comments: [],
      isLoading: false,
    };
  },
  methods: {
    async loadComments() {
      this.isLoading = true;
      try {
        const { data } = await axios.get(
          'https://jsonplaceholder.typicode.com/comments?_limit=42'
        );
        this.comments = data;
        this.isLoading = false;
      } catch (e) {
        this.isLoading = false;
        console.log(e.message);
      }
    },
  },
  components: { AppLoader, AppCommentCard },
};
</script>

<style lang="scss" scoped></style>
