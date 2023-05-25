<template>
  <ion-page>
    <div>
      <h1>Main View</h1>
      <div><button @click="openPage">Open Sub</button></div>
      <div><button @click="getList">Get List</button></div>
      <div><button @click="getDetail">Get Detail</button></div>
    </div>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage } from '@ionic/vue';
import { onIonViewWillEnter, onIonViewDidEnter, onIonViewWillLeave, onIonViewDidLeave } from '@ionic/vue';
import { useRouter } from 'vue-router';

const router = useRouter();

// 화면 Open
function openPage() {
  router.push('/sub');
}

// mock 데이터 조회
function getList() {
  fetch('/mock/list.json')
    .then(res => res.json())
    .then(data => {
      console.log(data);
      alert(JSON.stringify(data, null, '  '));
    })
}

function getDetail() {
  fetch('/mock/detail.json')
    .then(res => res.json())
    .then(data => {
      console.log(data);
      alert(JSON.stringify(data, null, '  '));
    })
}

// 화면 진입 애니메이션 표시 전
onIonViewWillEnter(() => {
  console.log('> Main page will enter');
});

// 화면 진입 애니메이션 표시 후
onIonViewDidEnter(() => {
  console.log('> Main page did enter');
});

// 화면 떠나기 애니메이션 표시 전
onIonViewWillLeave(() => {
  console.log('> Main page will leave');
});

// 화면 떠나기 애니메이션 표시 후
onIonViewDidLeave(() => {
  console.log('> Main page did leave');
});
</script>