<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Choices</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">

      <!-- List of current decision -->
      <ion-list>
        <ion-item v-for="item in choices" :key="item.title" color="primary" button>
          <ion-label> {{ item.title }} </ion-label>
        </ion-item>
      </ion-list>

      <ion-fab vertical="bottom" horizontal="end" slot="fixed">
        <ion-fab-button href="/tabs/choices/new"> <ion-icon :icon="add"></ion-icon> </ion-fab-button>
      </ion-fab>
      
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
// Import ionic component
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonFab,
  IonFabButton,
  IonList,
} from "@ionic/vue";

// Import ionic logo
import { add } from "ionicons/icons";

export default {
  name: "Choices",
  components: {
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonPage,
    IonFab,
    IonFabButton,
    IonList,
  },

  data: () => {
    return { 
      choices: [
        { title: "Choice 1" },
        { title: "Choice 2" },
        { title: "Choice 3" },
        { title: "Choice 4" }
      ]
    }
  },

  setup() {
    return {
      add,
    };
  },
};
</script>
