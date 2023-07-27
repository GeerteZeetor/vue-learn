<template>
  <form class="card card-w30" @submit.prevent="submitHandler">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type" v-model="value">
        <option value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea id="value" rows="3" v-model="text"></textarea>
    </div>

    <button type="submit" class="btn primary" :disabled="text.length < 3">
      Добавить
    </button>
  </form>
</template>

<script>
export default {
  emits: ['submit', 'onChange'],
  data() {
    return {
      value: 'title',
      text: '',
    };
  },
  methods: {
    submitHandler() {
      this.$emit('submit', {
        value: this.value,
        text: this.text,
        id: Date.now(),
      });
      this.value = 'title';
      this.text = '';
    },
  },
};
</script>

<style lang="scss" scoped></style>
