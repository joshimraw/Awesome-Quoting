<template>
	<div class="container">
		<app-newquote @quoteAdded="addNewQuote"></app-newquote>
		<hr>
		<app-quotegrid :quotes="quotes" @quoteDeleted="quoteDelete"></app-quotegrid>
	</div>
</template>


<script>
	import Newquote from './Newquote.vue';
	import Quotegrid from './Quotegrid.vue';
	export default{
		data: function(){
			return {
				quotes: [
					{ body: 'Somethign to display', title: 'Title of quote' }

				]
			}
		},
		components: {
			appQuotegrid: Quotegrid,
			appNewquote: Newquote
		},
		methods: {
			addNewQuote(quote){
				this.quotes.push(quote);
			},
			quoteDelete(index){
				this.quotes.splice(index, 1);
			}
		}
	}
</script>