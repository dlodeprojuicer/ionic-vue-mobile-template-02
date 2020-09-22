<template>
	<div>
		<div class="footer"></div>
		<ion-grid>
        <ion-row>
          <ion-col>
						<ion-icon :name="beer" class="force-down"></ion-icon>
          </ion-col>
          <ion-col>
						<div class="total">Total</div>
            <h3 class="force-down">R32</h3>
          </ion-col>
          <ion-col>
						<div class="pay">
							<ion-icon :name="card"></ion-icon>
							<h3>Pay</h3>
						</div>
          </ion-col>
        </ion-row>
		</ion-grid>
	</div>
</template>

<script>
import { IonGrid, IonRow, IonCol, IonIcon } from "@ionic/vue";
import { beer, card } from "ionicons/icons";

export default {
	name: "page2",
	components: { IonGrid, IonRow, IonCol, IonIcon },
  props: {
		data: {
			type: Array,
			required: true,
			default: () => []
		}
	},
  setup() {
    return {
      beer,
      card
    }
  },
	methods: {
		goto(route) {
			this.$emit("goto", route);
		}
	}
}
</script>

<style lang="scss" scoped>
.footer {
  position: fixed;
  bottom: 0;
	z-index: 999;
  width: 100%;
  height: 20%;
	background: #090a0e;
	clip-path: polygon(0% 0%, 100% 56%, 100% 100%, 0 100%)
  
}

ion-grid {
	position: fixed;
	bottom: 10px;
	z-index: 999999999;
	text-align: center;
	width: 100%;
	color: #b1b1b1;

	ion-col {
		margin: 0 20px;

		.force-down {
			margin-top: 50px;
		}
		
		ion-icon[name="card"] {
			font-size: 25px;
		}
		
		ion-icon[name="beer"] {
			font-size: 35px;
		}

		.total {
			font-weight: bold;
			margin: 33px 0 -40px 0;
		}

		.pay{
			border-radius: 15px;
			background: #272731;
			border: 1px #2f2f2f solid;
			padding: 20px 10px;
		}
	}
}
</style>
