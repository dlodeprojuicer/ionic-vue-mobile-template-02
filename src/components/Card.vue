<template>
	<div>
		<div class="card" @click="productView"></div>
		<h3>Blackberry</h3>
		<p>Fresh Drink</p>
	</div>
</template>

<script>

export default {
	name: "card",
	methods: {
		productView() {
			this.$emit("productview");
		}
	}
}
</script>

<style lang="scss" scoped>
.card {
	background: #000000;
  background-image: url("/assets/img/b.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
	border-radius: 30px;
	height: 370px;
  // height: 60%; somehow % is not working
	margin: 0 3px;
}

h3 {
	padding: 0 0 0 30px;
	color: #d6d6d6;
	font-size: 30px;
	font-weight: 600;
	margin: -90px 0 -15px 0;
	z-index: 9999999999;
}

p {
	padding: 0 0 0 30px;
	color: #a7a7a7;
	font-weight: 500;
}
</style>
