<template>
  <div>
    <h1>Contact Information</h1>
    <form>
      <div class="form-group">
        <label for="name">Name:</label>
        <input v-model="formData.name" type="text" id="name">
      </div>

      <div class="form-group">
        <label for="email">Email:</label>
        <input v-model="formData.email" type="email" id="email">
      </div>

      <div class="form-group">
        <label for="phone">Phone:</label>
        <input v-model="formData.phone" type="tel" id="phone">
      </div>
    </form>

    <div class="result">
      <h2>Entered Information:</h2>
      <p><strong>Name:</strong> {{ formData.name }}</p>
      <p><strong>Email:</strong> {{ formData.email }}</p>
      <p><strong>Phone:</strong> {{ formData.phone }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        name: '',
        email: '',
        phone: ''
      }
    }
  }
}
</script>
