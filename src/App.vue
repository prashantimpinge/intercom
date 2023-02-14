<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<style>
ion-content{ 
  font-family:ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  height: 100%;
}
</style>

<script setup>
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import { ref, onMounted } from 'vue';
import axios from "axios"

const ipAddress  = ref()

window.intercomSettings = {
  app_id: "pnsu3l0n",
  custom_launcher_selector: ".intercom_chat",
  chatPartner: "MOBILEAPP"
};

// We pre-filled your app ID in the widget URL: 'https://widget.intercom.io/widget/pnsu3l0n'
(function(){var w=window;var ic=w.Intercom;if(typeof ic==="function"){ic('reattach_activator');ic('update',w.intercomSettings);}else{var d=document;var i=function(){i.c(arguments);};i.q=[];i.c=function(args){i.q.push(args);};w.Intercom=i;var l=function(){var s=d.createElement('script');s.type='text/javascript';s.async=true;s.src='https://widget.intercom.io/widget/pnsu3l0n';var x=d.getElementsByTagName('script')[0];x.parentNode.insertBefore(s,x);};if(w.attachEvent){w.attachEvent('onload',l);}else{w.addEventListener('load',l,false);}}})();

onMounted( async () => {
  const res = await axios.get("https://api.ipify.org/?format=json");
  ipAddress.value = res.data.ip;
  window.Intercom("update", {ipaddress: ipAddress.value});
});
</script>