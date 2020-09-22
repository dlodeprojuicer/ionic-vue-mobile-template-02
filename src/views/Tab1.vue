<template>
  <ion-page>
    <div id="container">
      <ion-grid>
        <ion-row>
          <ion-col>
            <h3>Type</h3>
            <h2>Small</h2>
            <h3>Place</h3>
            <h2>Outdoor</h2>
          </ion-col>
          <ion-col>
            <img src="assets/img/360.jpeg" class="image" />
          </ion-col>
        </ion-row>
      </ion-grid>

      <ion-grid>
        <ion-row>
          <ion-col>
            <ion-item>
              <ion-icon :icon="chevronBackCircle" slot="start" />
              <ion-label>
                <h2>Rey</h2>
                <h3>I can handle myself</h3>
                <p>You will remove these restraints and leave...</p>
              </ion-label>
            </ion-item>
          </ion-col>
          <ion-col>
            <ion-item>
              <ion-icon :icon="chevronBackCircle" slot="start" />
              <ion-label>
                <h2>Rey</h2>
                <h3>I can handle myself</h3>
                <p>You will remove these restraints and leave...</p>
              </ion-label>
            </ion-item>
          </ion-col>
        </ion-row>
      </ion-grid>
    </div>
  </ion-page>
</template>

<script>
import {
  IonPage,
  IonGrid,
  IonRow,
  IonCol,
  IonIcon,
  IonLabel,
  IonItem,
} from "@ionic/vue";
import { chevronBackCircle } from "ionicons/icons";

export default {
  name: "Dashboard",
  components: { IonPage, IonGrid, IonRow, IonCol, IonIcon, IonLabel, IonItem },
  setup() {
    return {
      chevronBackCircle,
    };
  },
};
</script>

<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 35%;
  transform: translateY(-50%);
}

img {
  width: 100px;
  height: 100px;
  border-radius: 50%;
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

ion-button {
  margin-top: 200px;
}
</style>