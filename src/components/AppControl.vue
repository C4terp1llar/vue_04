<template>
  <form class="card card-w30" @submit.prevent="handleSubmit">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type"
              v-model="typeInfo"
      >
        <option value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea id="value" rows="3" v-model="val"></textarea>
    </div>

    <button class="btn primary" :disabled="val.length<3 || !typeInfo">Добавить</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      typeInfo: 'title',
      val: '',
      localId: 0
    };
  },
  methods: {
    handleSubmit() {
      this.$emit('change', {
        id: this.localId ++,
        type: this.typeInfo,
        value: this.val
      });

      this.val = '';
      this.typeInfo = 'title';
    }
  },
  emits: ['change']
};
</script>

<style lang="">
    
</style>