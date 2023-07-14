<template>
  <div class="form-generator">
    <form class="form" @submit.prevent="handleSubmit">
      <slot></slot>
      <button type="submit">Save</button>
      <button type="button" @click="handleCancel">Clear</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'FormGenerator',
  methods: {
    handleSubmit() {
      this.$emit('submit');
    },
    handleCancel() {
      this.$emit('clear');
    },
  },
};
</script>

<style lang="scss" scoped>
.form {
  margin-top: 20px;
  border: 1px solid #ccc;
  padding: 30px;
}

.form-generator {
  margin-bottom: 20px;
}

.form-item {
  display: flex;
  flex-direction: column;
  margin-bottom: 10px;
}

.form-item label {
  margin-bottom: 5px;
}

input {
  border: 1px solid;
  border-radius: 3px;
}

.form-item-chekbox {
  flex-direction: row;
  align-items: center;
}

button {
  margin-top: 10px;
}
</style>
