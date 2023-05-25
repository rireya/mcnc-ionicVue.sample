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
import { onIonViewWillEnter, onIonViewDidEnter, onIonViewWillLeave, onIonViewDidLeave } from '@ionic/vue';
import { useRouter } from 'vue-router';

const router = useRouter();

function closePage() {
  router.back();
}

// 화면 진입 애니메이션 표시 전
onIonViewWillEnter(() => {
  console.log('>> Sub page will enter');
});

// 화면 진입 애니메이션 표시 후
onIonViewDidEnter(() => {
  console.log('>> Sub page did enter');
});

// 화면 떠나기 애니메이션 표시 전
onIonViewWillLeave(() => {
  console.log('>> Sub page will leave');
});

// 화면 떠나기 애니메이션 표시 후
onIonViewDidLeave(() => {
  console.log('>> Sub page did leave');
});
</script>