<template>
    <div class="max-w-md mx-auto mt-10 p-6 bg-white rounded-xl shadow-md">
      <h2 class="text-2xl font-bold mb-4 text-center">Đăng nhập</h2>
      <form @submit.prevent="handleLogin">
        <div class="mb-4">
          <label class="block text-gray-700 mb-1">Email</label>
          <input
            type="email"
            v-model="email"
            class="w-full px-3 py-2 border rounded-md focus:outline-none focus:ring"
            placeholder="Nhập email"
          />
          <p v-if="errors.email" class="text-red-500 text-sm">{{ errors.email }}</p>
        </div>
  
        <div class="mb-4">
          <label class="block text-gray-700 mb-1">Mật khẩu</label>
          <input
            type="password"
            v-model="password"
            class="w-full px-3 py-2 border rounded-md focus:outline-none focus:ring"
            placeholder="Nhập mật khẩu"
          />
          <p v-if="errors.password" class="text-red-500 text-sm">{{ errors.password }}</p>
        </div>
  
        <button
          type="submit"
          class="w-full bg-blue-500 text-white py-2 rounded-md hover:bg-blue-600 transition"
        >
          Đăng nhập
        </button>
      </form>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const email = ref('')
  const password = ref('')
  const errors = ref({})
  
  const handleLogin = () => {
    errors.value = {}
  
    if (!email.value) {
      errors.value.email = 'Email không được để trống'
    }
  
    if (!password.value) {
      errors.value.password = 'Mật khẩu không được để trống'
    }
  
    if (Object.keys(errors.value).length === 0) {
      // Gửi API đăng nhập tại đây
      console.log('Đăng nhập với', { email: email.value, password: password.value })
    }
  }
  </script>
  
  <style scoped>
  </style>
  