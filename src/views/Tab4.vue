<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 4</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 4</ion-title>
          
        </ion-toolbar>
      </ion-header>
    
      <ExploreContainer name="Tab 4 page" />
      <h5>- tab mostrar se a pessa esta no vermelho ou não</h5>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
//import ExploreContainer from '@/components/ExploreContainer.vue';

export default  {
  name: 'Tab4',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage }
}
</script>