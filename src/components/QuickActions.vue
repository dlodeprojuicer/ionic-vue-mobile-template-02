<template>
  <ion-grid>
    <ion-row id="list">
      <ion-col v-for="(item, index) in btns" :key="index" @click="select(index)" :class="active === index ? 'active' : null">
        {{ item }}
      </ion-col>
    </ion-row>
  </ion-grid>
</template>

<script>
import { IonGrid, IonRow, IonCol } from "@ionic/vue";

export default {
  name: "quick-actions",
  components: { IonGrid, IonRow, IonCol },
  data() {
    return {
      active: null,
      btns: ["Promotion", "Free Drink", "Happy Hour"]
    }
  },
	methods: {
		pay() {
			this.$router.push("pay");
    },
    select(index) {
      this.active = index;
    }
	}
};
</script>

<style lang="scss" scoped>
ion-grid {
  margin-bottom: 20px;
}

ion-col {
  // background: #0f0f17;
  color: #838688;
  padding: 7px;
  text-align: center;
  font-weight: 500;
  margin: 5px;
  border-radius: 20px;

  // &:first-child {
  //   border: 1px #2f2f2f solid;
  //   color: #d0cdcd;
  // }
}

.active {
  border: 1px #2f2f2f solid;
}

.btn-icon {
  margin: -3px 5px;
}
</style>