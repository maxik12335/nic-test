<template>
  <div id="app">
    <h1>Form Generator App</h1>
    <FormGenerator @submit="handleSubmit" @clear="handleClear">
      <div class="form-data-container">
        <div class="form-item">
          <label for="name">Name:</label>
          <input type="text" id="name" v-model="formData.name" />
        </div>
        <div class="form-item">
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="formData.email" />
        </div>
        <div class="form-item">
          <label for="message">Message:</label>
          <textarea id="message" v-model="formData.message"></textarea>
        </div>
        <div class="form-item">
          <label for="gender">Gender:</label>
          <select id="gender" v-model="formData.gender">
            <option value="male">Male</option>
            <option value="female">Female</option>
          </select>
        </div>
        <div class="form-item form-item-chekbox">
          <label for="agree">Agree:</label>
          <input type="checkbox" id="agree" v-model="formData.agree" />
        </div>
      </div>
    </FormGenerator>
  </div>
</template>

<script>
import FormGenerator from './components/FormGenerator.vue';

export default {
  name: 'App',
  components: {
    FormGenerator,
  },
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: '',
        gender: '',
        agree: false,
      },
    };
  },
  methods: {
    handleSubmit() {
      console.log('Form submitted:', this.formData);
    },
    handleClear() {
      console.log('Form clear');
      this.formData = {
        name: '',
        email: '',
        message: '',
        gender: '',
        agree: false,
      }
    },
  },

  mounted() {
    console.log("Fetch")
  }
};
</script>

<style lang="scss">
#app {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

input:focus,
textarea:focus,
select:focus {
  outline: none;
}
</style>
