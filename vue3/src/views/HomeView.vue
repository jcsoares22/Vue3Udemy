<template>
  <v-app>
    <router-view />
    <v-footer app color="primary" dark>
      <v-container>
        <v-row justify="center">
          <v-col cols="12">
            <v-btn color="white" text @click="logout">
              Sair
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';
const authStore = useAuthStore();
const router = useRouter();


const logout = () => {
  authStore.logout();
  console.log('Usuário deslogado');
  router.push('/login');
};
</script>

<style scoped>
.v-list-item {
  margin: 8px 0;
}
.v-list-item--active {
  background-color: #e3f2fd;
  color: #1976d2;
}
</style>
