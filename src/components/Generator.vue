<template>
	<div>
		<h1>{{ title }}</h1>
		<div>
      <input type="text" size="25" placeholder="Type..." v-model="text" debounce="500" />
    </div>

		<div v-if="text" class="output">
			<qr-code :text="text"></qr-code>
		</div>
	</div>
</template>

<script>
import VueQRCodeComponent from "vue-qrcode-component";

export default {
	name: "Generator",
	data() {
		return {
			title: "QRCode Generator",
			text: "https://arnon.dev",
		};
	},
  components: { "qr-code": VueQRCodeComponent },
};
</script>

<style scoped>
@font-face {
	font-family: "RobotoMono";
	src: url("../fonts/RobotoMono-Thin.ttf");
}

* {
	font-family: "RobotoMono", monospace;
}

input {
	font-size: 2em;
	margin-bottom: 30px;
}

.output {
	border: 1px solid #222;
	padding: 30px 15px;
	background-color: #0006;
	text-align: -webkit-center;
}

@media (max-width: 600px) {
	input {
		font-size: 1.5em;
	}
	.output {
		width: 300px;
		margin: auto;
	}
}

@media (max-width: 400px) {
	h1 {
		font-size: 1.5em;
	}
	input {
		font-size: 1em;
	}
	.output {
		width: 260px;
		margin: auto;
	}
}
</style>