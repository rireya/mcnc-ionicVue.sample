<template>
  <ion-page>
    <div>
      <h1>Sub View</h1>
      <button @click="closePage">Close Sub</button>
    </div>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage } from '@ionic/vue';
import { useRouter } from 'vue-router';

const router = useRouter();

function closePage() {
  router.back();
}
</script>