<template>
  <div>
    <div v-if="loading">Loading...</div>
    <div v-else class="grid grid-cols-2 gap-4 pt-4">
      <userCard
        v-for="(profile, index) in userStore.allProfiles.value"
        :key="index"
        :profile="profile"
      />
    </div>
  </div>
</template>

<script setup>
import { useUserStore } from "@/stores/userStore";
const userStore = useUserStore();

const loading = ref(true);

onMounted(async () => {
  await userStore.fetchProfiles();
  console.log("Profiles: ", userStore.allProfiles.value);
  loading.value = false;
});
</script>

<style></style>
