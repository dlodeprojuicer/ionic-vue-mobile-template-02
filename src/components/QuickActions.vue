<template>
  <ion-grid>
    <ion-row id="list">
      <ion-col v-for="(item, index) in btns" :key="index" @click="select(index)" :class="active === index ? 'active' : null">
        {{ item }}
      </ion-col>
    </ion-row>
  </ion-grid>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { IonGrid, IonRow, IonCol } from "@ionic/vue";

defineOptions({
  name: "quick-actions"
});

const active = ref<number | null>(null);
const btns = ["Promotion", "Free Drink", "Happy Hour"];

const select = (index: number) => {
  active.value = index;
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
