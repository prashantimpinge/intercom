<template>
  <ion-page>
    <ion-content>
      <div class="app bg-slate-50 h-full">
        <div class="max-w-screen-lg mx-auto h-full">
          <main class="main-wrapper h-full">
            <div class="main-content flex flex-col justify-between h-full">
              <div class="flex flex-col">
                <div class="flex px-6">
                  <router-link to="/feedback" class="ml-auto w-16 sm:w-20">
                    
                  </router-link>
                </div>
                <div class="flex justify-center pt-6 pb-6 px-6 sm:pb-10">
                  <div class="w-3/4 mx-auto sm:w-1/3">
                    
                  </div>
                </div>
              </div>
              <div class="flex flex-col">
                <div>
                  <router-link to="/gethelp" class="flex items-center py-4 btn btn-1 sm:py-6">
                    <span class="btn-icon">
                      <img src="images/get_help_icon.png" alt="" />
                    </span>
                    <span class="pl-8 uppercase font-bold btn-text"
                      >Get Help</span
                    >
                  </router-link>
                </div>
                <div>
                  <a @click="openExternalSite('https://www.thehopeline.com/topics/?utm_source=mobileapp&utm_medium=choosetopicpage&utm_campaign=homepage-mobileapp')" class="flex items-center py-4 btn btn-2 sm:py-6">
                    <span class="btn-icon">
                      
                    </span>
                    <span class="pl-8 uppercase font-bold btn-text"
                      >Find your issue</span
                    >
                  </a>
                </div>
                <div>
                  <a @click="openExternalSite('https://www.thehopeline.com/suicide-prevention-resources/?utm_source=mobileapp&utm_medium=suicideprevention&utm_campaign=homepage-mobileapp')" class="flex items-center py-4 btn btn-3 sm:py-6">
                    <span class="btn-icon">
                      
                    </span>
                    <span class="pl-8 uppercase font-bold btn-text"
                      >Suicide resources</span
                    >
                  </a>
                </div>
                <div>
                  <a @click="openExternalSite('https://www.thehopeline.com/subscription-page/?utm_source=mobileapp&utm_medium=subscribe&utm_campaign=homepage-mobileapp')" class="flex items-center py-4 btn btn-4 sm:py-6">
                    <span class="btn-icon">
                      
                    </span>
                    <span class="pl-8 uppercase font-bold btn-text"
                      >Subscribe</span
                    >
                  </a>
                </div>
              </div>
              <div class="flex flex-col justify-center pt-6 pb-2 px-6 text-center sm:pb-4 sm:pt-10">
                <div class="mb-5">
                  <h2
                    class="uppercase font-bold text-2xl sm:text-4xl"
                    style="color: #1e435b"
                  >
                    Chat live with <br />
                    a hope coach
                  </h2>
                </div>
                <div class="w-5/12 mx-auto sm:w-1/3">
                  
                </div>
              </div>
            </div>
          </main>
        </div>
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
.main-wrapper {
  background-repeat-y: repeat;
  background-size: contain;
}
.btn-1 {
  background-color: #dadfe2;
  color: #1e435b;
}
.btn-2 {
  background-color: #85becc;
  color: #ffffff;
}
.btn-3 {
  background-color: #f5e680;
  color: #1e435b;
}
.btn-4 {
  background-color: #1e435b;
  color: #ffffff;
}
.btn {
  padding-left: 12%;
  padding-right: 6%;
}
.btn-icon {
  width: 10%;
  min-width: 10%;
}
.btn-text {
  font-size: 120%;
  line-height: 1;
  letter-spacing: -1px;
}
@media (min-width: 375px) {
  .btn-text {
    font-size: 125%;
    line-height: 1;
  }
}
@media (min-width: 481px) {
  .btn-text {
    font-size: 200%;
    line-height: 1;
  }
}
@media (min-width: 590px) {
  .btn-text {
    font-size: 250%;
    line-height: 1;
  }
  .btn-icon {
    width: 7%;
    min-width: 7%;
  }
}
</style>