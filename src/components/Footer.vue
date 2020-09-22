<template>
	<div class="footer">
		<ion-tabs>
			<ion-tab-bar>
				<ion-tab-button :tab="item.label" v-for="(item, index) in data" :key="index" @click="goto(item.route)">
					<ion-icon :icon="item.icon"></ion-icon>
				</ion-tab-button>
			</ion-tab-bar>
		</ion-tabs>
	</div>
</template>

<script>
import { IonTabs, IonTabBar, IonTabButton, IonIcon } from "@ionic/vue";

export default {
	name: "page-footer",
	components: { IonTabs, IonTabBar, IonTabButton, IonIcon },
  props: {
		data: {
			type: Array,
			required: true,
			default: () => []
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
// .footer {
//   position: fixed;
//   bottom: 100px;
// 	z-index: 999;
//   width: 100%;
// }

ion-tab-bar {
	padding: 0 10px;
	height: 100px;
	--background: #000000;
}

ion-tab-button {
	height: 40px;
	margin: 15px;

	&:first-child {
		border-radius: 40px;
		background: #262626;
    border: 1px #2f2f2f solid;
    color: #717070;
  }
}
</style>
