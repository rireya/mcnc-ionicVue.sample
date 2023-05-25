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
</script>