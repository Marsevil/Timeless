<template>
  <ion-page>
    <ion-header class="ion-padding-top">
      <ion-toolbar>
        <ion-title>Create new choice</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">

        <ion-item class="ion-padding-bottom">
            <ion-label position="stacked"> Choice name : </ion-label>
            <ion-input placeholder="name"></ion-input>
        </ion-item>

        <ion-list lines="full">
            <ion-list-header lines="full">
                <ion-title> Options </ion-title>
            </ion-list-header>

            <ion-item>
                <ion-label position="floating"> Option 1 </ion-label>
                <ion-input></ion-input>
            </ion-item>

            <ion-item>
                <ion-label position="floating"> Option 2 </ion-label>
                <ion-input></ion-input>
            </ion-item>

        </ion-list>

      <!-- Cancel button -->
      <ion-fab vertical="bottom" horizontal="start" slot="fixed">
          <ion-fab-button color="danger" href="/tabs/choices">
              <ion-icon :icon="close"></ion-icon>
          </ion-fab-button>
      </ion-fab>

      <!-- Validate button -->
      <ion-fab vertical="bottom" horizontal="end" slot="fixed">
        <ion-fab-button color="success">
          <ion-icon :icon="checkmarkOutline"></ion-icon>
        </ion-fab-button>
      </ion-fab>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonFab,
  IonFabButton,
  IonInput,
  IonList,
  IonListHeader
} from "@ionic/vue";

// import ionic icon
import { checkmarkOutline, close } from "ionicons/icons";

export default {
  name: "NewChoice",
  components: {
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonPage,
    IonFab,
    IonFabButton,
    IonInput,
    IonList,
    IonListHeader
  },

  setup: () => {
    return {
      checkmarkOutline,
      close
    };
  },
};
</script>