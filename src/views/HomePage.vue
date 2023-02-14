<template>
  <ion-page>
    <ion-content>
      <div class="app bg-slate-50 h-full">
         Hello
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup>
import { IonContent, IonPage } from "@ionic/vue";
import { Browser } from '@capacitor/browser';

const openExternalSite = async (url) => {
  await Browser.open({ url: url });
};
window.Intercom('update', {
  hide_default_launcher: false,
});
</script>

<style scoped>

</style>