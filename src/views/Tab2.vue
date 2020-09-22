<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>
          <ion-icon :icon="chevronBackCircle" />
          Spending Breakdown
        </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
       <div>
        <ion-item>
          <ion-label>Include subscription & bills</ion-label>
          <ion-toggle color="primary"></ion-toggle>
        </ion-item>

        <ion-list>
          <ion-list-header>
            Frequent Spend
          </ion-list-header>
            <ion-item v-for="(item, index) in frequentSpend" :key="index">
              <ion-label>{{ item.name }}</ion-label>
              <ion-note slot="end" color="danger">{{ item.price }}</ion-note>
            </ion-item>
        </ion-list>
       </div>
    </ion-content>
  </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonIcon, IonToolbar, IonTitle, IonContent, IonList, IonItem, IonLabel, IonNote, IonListHeader, IonToggle } from '@ionic/vue';
import { chevronBackCircle } from 'ionicons/icons';

export default  {
  name: 'Spending',
  components: { IonHeader, IonIcon, IonToolbar, IonTitle, IonContent, IonPage, IonList, IonItem, IonLabel, IonNote, IonListHeader, IonToggle },
  setup() {
    return {
      chevronBackCircle
    }
  },
  data() {
    return {
      frequentSpend: [
        {
          name: "Rent apartment",
          price: "$820"
        },
        {
          name: "Dinning",
          price: "$460"
        },
        {
          name: "Shopping",
          price: "$310"
        },
        {
          name: "Utilities",
          price: "$110"
        },
        {
          name: "Other",
          price: "$80"
        }
      ]
    }
  }
}
</script>