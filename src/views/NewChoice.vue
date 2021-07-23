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
            <ion-input v-model="name" placeholder="name"></ion-input>
        </ion-item>

        <ion-list lines="full">
            <ion-list-header lines="full">
                <ion-title> Options </ion-title>
            </ion-list-header>

            <ion-item>
                <ion-label position="floating"> Option 1 </ion-label>
                <ion-input v-model="option1"></ion-input>
            </ion-item>

            <ion-item>
                <ion-label position="floating"> Option 2 </ion-label>
                <ion-input v-model="option2"></ion-input>
            </ion-item>

        </ion-list>

      <!-- Cancel button -->
      <ion-fab vertical="bottom" horizontal="start" slot="fixed">
          <ion-fab-button color="danger" router-link="/tabs/choices" @click="resetData();">
              <ion-icon :icon="close"></ion-icon>
          </ion-fab-button>
      </ion-fab>

      <!-- Validate button -->
      <ion-fab vertical="bottom" horizontal="end" slot="fixed">
        <ion-fab-button color="success" @click="valid();">
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
  IonListHeader,
  IonIcon,
  IonItem,
  IonLabel,
  alertController
} from "@ionic/vue";

import { defineComponent } from "@vue/runtime-core";

// import ionic icon
import { checkmarkOutline, close } from "ionicons/icons";

export default defineComponent({
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
    IonListHeader,
    IonIcon,
    IonItem,
    IonLabel
  },

  data() {
    return {
      name: "",
      option1: "",
      option2: ""
    };
  },

  setup() {
    return {
      checkmarkOutline,
      close,
    };
  },

  methods: {
    resetData() {      
      this.name = "";
      this.option1 = "";
      this.option2 = "";
    },

    async valid() {
      if (this.name != "" && this.option1 != "" && this.option2 != "") {
        // Process data
        console.log({
          name: this.name,
          option1: this.option1,
          option2: this.option2
        });

        // Reset and move to the main page
        this.$router.push("/tabs/choices");
        this.resetData();
      } else {
        // Send an alert
        const alert = await alertController.create({
          header: 'Error',
          message: 'Fields should not be empty',
          buttons: ['OK']
        });

        await alert.present();
      }

    },
  }
});
</script>