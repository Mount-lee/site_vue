<script>
	export default {
		data () {
			return {
				currency: ""
			}
		}
	}
</script>

<template>
	<div id="cur_page_back">
		<h5><a href="/index.html">Прогноз погоды</a></h5>
	</div>
	<div id="cur_page_top">
		<h1>Конвертер валют</h1>
		<p>Выберите валюту</p>
	</div>
	<div id="cur_page">
		<form>
			<select id="cur_1">
				<option>USD</option>
				<option>EUR</option>
				<option>TRY</option>
				<option>RUB</option>
				<option>GEL</option>
			</select><br>
			<select id="cur_2">
				<option>EUR</option>
				<option>USD</option>
				<option>TRY</option>
				<option>RUB</option>
				<option>GEL</option>
			</select><br>
			<input type="text" v-model="currency" placeholder="Введите сумму"><br>
			<button v-if="currency != ''">Конвертировать</button>
			<button disabled v-else>Конвертировать</button>

		</form>
	</div>
</template>

<style scoped>
	
</style>