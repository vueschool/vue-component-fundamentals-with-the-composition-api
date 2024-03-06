<script setup>
import { ref } from 'vue'
const props = defineProps({
  username: { type: String, required: true }
})

const user = ref()

fetch(`https://api.github.com/users/${props.username}`).then(async (res) => {
  const data = await res.json()
  user.value = data
})
</script>
<template>
  <div v-if="user" class="m-5 shadow-xl card card-side bg-base-100">
    <figure>
      <img :src="user.avatar_url" alt="Movie" />
    </figure>
    <div class="card-body">
      <h2 class="card-title">{{ user.name }}</h2>
      <p>
        <strong>Followers:</strong> {{ user.followers }} <strong>Following:</strong>
        {{ user.following }}
      </p>
      <div class="justify-end card-actions">
        <a :href="user.html_url" class="btn btn-primary">View Profile</a>
      </div>
    </div>
  </div>
</template>
