<template>
	<Generator />
</template>

<script>
import Generator from "@/components/Generator.vue";

export default {
	name: "App",
  components: { Generator },
  created() {
    document.title = "QRCode Generator";
  },
};
</script>

<style>
body {
	display: flex;
	justify-content: center;
	text-align: center;
	color: #fff;
	background: linear-gradient(to right, rgb(19, 106, 138), rgb(38, 120, 113));
}
</style>
