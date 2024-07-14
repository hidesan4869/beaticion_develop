<script>
import { Head, Link, useForm } from '@inertiajs/vue3';

export default {
  setup() {
    const form = useForm({
      email: '',
      password: ''
    });

    const login = () => {
      form.post(route('admin.login'));
    };

    return { form, login };
  }
};
</script>

<template>
    <div>
      <h1>Admin Login</h1>
      <form @submit.prevent="login">
        <div>
          <label for="email">Email:</label>
          <input v-model="form.email" type="email" id="email" name="email" required>
        </div>
        <div>
          <label for="password">Password:</label>
          <input v-model="form.password" type="password" id="password" name="password" required>
        </div>
        <button type="submit">Login</button>
      </form>
    </div>
  </template>

