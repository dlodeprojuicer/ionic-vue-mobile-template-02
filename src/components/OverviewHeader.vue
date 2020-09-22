<template>
	<div class="header">
		<ion-icon :icon="arrowBack" class="back"  @click="back"></ion-icon>
	</div>
</template>

<script>
import { IonIcon } from "@ionic/vue";
import { arrowBack } from "ionicons/icons";

export default {
	name: "overview-header",
	components: { IonIcon },
	setup() {
    return {
      arrowBack
    }
  },
  methods: {
		back() {
			this.$router.back();
		}
	}
}
</script>

<style lang="scss" scoped>
.header {
	background: #000000;
  background-image: url("/assets/img/b.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
	height: 45%;
	padding: 15px 0 0 15px;
	z-index: -99999999999;
}

ion-icon {
	font-size: 18px;
	background: #1d1d23;
	padding: 13px;
	color: #ffffff;
	border-radius: 50px;
	font-weight: 600;

	&.back {
		border-radius: 10px;
	}
}
</style>
