<template>
	<div class="row">
		<form>
			<div class="col-md-6 col-md-offset-3 form-group">
				<label class="lead">Add New Quote</label>
				<input type="text" class="form-control" placeholder="your title here" v-model="quotes.title">
			</div>
			<div class="col-md-6 col-md-offset-3 form-group">
				<textarea class="form-control" rows="3" 
				v-model="quotes.body" @keyup.enter="addNew" placeholder="write something here"> </textarea>
			</div>

			<div class="col-md-6 col-md-offset-3 form-group">
			<button class="btn btn-primary pull-right" @click.prevent="addNew">Submit</button>
			</div>
		</form>
	</div>
</template>

<script>
	export default{
		data: function(){
			return {
				quotes: {
					body: '',
					title: ''
				}
			}
		},
		methods: {
			addNew(quote){
				this.$emit('quoteAdded', this.quotes);
				this.quotes = '';
			}
		}
	}
</script>