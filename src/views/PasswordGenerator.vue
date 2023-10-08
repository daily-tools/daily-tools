<template>
  <v-container>
	<h1 class="text-center">Generate a secure password</h1>
	<p class="text-center">
		Use our online password generator to instantly create a secure, random password.
	</p>
	<v-sheet
		color="white"
		elevation="6"
		outlined
	>
		<v-row>
			<v-col cols="12" offset-md="2" md="8">
				<v-form ref="form">
					<v-text-field
						v-model="password"  readonly class="text-center"
					></v-text-field>

					<v-slider
						v-model="passwordLength"
						thumb-label="always"
						class="mt-5"
						label="Password Length:"
						min="1"
						max="30"
						@input="generatePassword()"
					></v-slider>

					<v-row align="center" justify="center">
						<v-btn-toggle v-model="toggle" class="btn-toggle" multiple @change="generatePassword()" >
							<v-btn color="#00bcd4" value="lowercase">Lower-Case (a-z)</v-btn>
							<v-btn color="#00bcd4" value="uppercase">Upper-Case (A-Z)</v-btn>
							<v-btn color="#00bcd4" value="numbers">Numbers (0-9)</v-btn>
							<v-btn color="#00bcd4"  value="symbols">Symbols (*-_/)</v-btn>
						</v-btn-toggle>
					</v-row>
					<v-btn
						block
						dark
						x-large
						class="mt-10 mb-10"
						@click="generatePassword()"
					>Generate</v-btn>
				</v-form>
			</v-col>
		</v-row>
	</v-sheet>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'
import generator from "generate-password-browser";

@Component()
export default class PasswordGenerator extends Vue {
	data() {
		return {
			password: "",
			passwordLength: 14,
			toggle: ["lowercase", "uppercase", "numbers"],
		}
	}
	generatePassword() {
		this.password = generator.generate({
			length: this.passwordLength,
			numbers: this.toggle.includes("numbers"),
			symbols: this.toggle.includes("symbols"),
			lowercase: this.toggle.includes("lowercase"),
			uppercase: this.toggle.includes("uppercase"),
			strict: true,
		});
	}
	mounted() {
		this.generatePassword();
	}
}
</script>
<style lang="scss">
.btn-toggle, .btn-toggle .theme--light.v-btn {
	color: white;
}
</style>