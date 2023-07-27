<template>
  <div class="card">
    <h2>Комментарии</h2>
    <ul class="list" v-for="comment in comments" :key="comment.id">
      <li class="list-item">
        <div>
          <p>
            <strong>{{ comment.email }}</strong>
          </p>
          <small>{{ comment.body }}}</small>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['comments'],
};
</script>

<style lang="scss" scoped></style>
