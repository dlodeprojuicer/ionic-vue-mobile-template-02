<template>
  <ion-page class="ion-padding">
    <ion-content>
      <ion-grid class="overview-wrapper">
        <ion-row>
          <ion-col>
            <h2 class="overview">Tonight</h2>
            <div class="date">Monday, November 25</div>
          </ion-col>
          <ion-col>
            <div class="price">
              R32
              <p class="total-price">Total Price</p>
            </div>
          </ion-col>
        </ion-row>
      </ion-grid>

      <QuickActions />

      <Card @productview="productview" />
    </ion-content>
  </ion-page>
</template>


<script setup lang="ts">
import { IonPage, IonGrid, IonRow, IonCol, IonContent } from "@ionic/vue";
import { useRouter } from "vue-router";

import Card from "../components/Card.vue";
import QuickActions from "../components/QuickActions.vue";

defineOptions({
  name: "home"
});

const router = useRouter();

const productview = () => {
  router.push("product-view");
};
</script>


<style lang="scss" scoped>
.overview-wrapper {
  margin-bottom: 10px;
}

.overview {
  color: #ffffff;
  font-size: 40px;
  font-weight: 500;
}

.overview-add {
  background: #ffffff;
  padding: 0px;
  border-radius: 10px;
  color: #000;
  float: right;
  font-size: 28px;
}

.price {
  background: #312F3E;
  width: fit-content;
  padding: 20px 7px;
  border-radius: 15px;
  float: right;
  color: #cecbcb;
  font-size: 20px;
  font-weight: bold;
  text-align: center;

  .total-price {
    font-weight: normal;
    margin-top: 7px;
    font-size: 10px;
    color: #838688;
  }
}

.date {
  color: #838688;
}
</style>
