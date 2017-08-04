<template>
	<div class="row">
	<div class="col-md-6 col-md-offset-3">
		<div class="panel panel-success" v-for="(quote, index) in quotes">
			<div class="panel-heading">{{ quote.title }} 
			<span class="close glyphicon glyphicon-remove" @click="deleteQuote(index)"></span></div>
			<div class="panel-body"> {{ quote.body }} </div>
		</div>
	</div>
	</div>
</template>

<script>

	export default{
		props: ['quotes'],

		methods: {
			deleteQuote(index){
				this.$emit('quoteDeleted', index);
			}
		}
	}
</script>

<style>

	.panel{
		cursor: pointer;
	}
	.panel:hover{
		background: #ffe2e2;
	}
</style>