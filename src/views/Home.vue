<template>
  <ion-page class="ion-padding">
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

  </ion-page>
</template>


<script>
import { IonPage, IonGrid, IonRow, IonCol } from "@ionic/vue";

import Card from "../components/Card";
import QuickActions from "../components/QuickActions";

export default {
  name: "home",
  title: "Home",
  requiresAuth: false,
  components: {
    IonPage,
    IonGrid,
    IonRow,
    IonCol,
    QuickActions,
    Card
  },
  data() {
    return {
      cards: [
        {
          cardNumber: "4524 3428 898 239",
          balance: "12 354.05",
          accountName: "Savings",
          expDate: "02/2020",
        },
        {
          cardNumber: "9483 2394 8987 8391",
          balance: "1435.20",
          accountName: "Savings",
          expDate: "06/2024",
        },
        {
          cardNumber: "3079 485 2395 3944",
          balance: "8 200",
          accountName: "Savings",
          expDate: "08/2022",
        },
      ],
      recentList: [
        {
          name: "Themna Makwa",
          icon: "person",
          cost: "19.30",
          date: "12 Aug 2020, 03:23 am",
        },
        {
          name: "Tami Muthambi",
          icon: "person",
          cost: "6.09",
          date: "10 Aug 2020, 13:40 pm",
        },
        {
          name: "Gary Goat",
          icon: "person",
          cost: "19.30",
          date: "12 Aug 2020, 03:23 am",
        },
        {
          name: "Jackie Chan",
          icon: "person",
          cost: "6.09",
          date: "10 Aug 2020, 13:40 pm",
        },
      ],
    };
  },
  methods: {
    productview() {
      this.$router.push("product-view");
    }
  }
}
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

