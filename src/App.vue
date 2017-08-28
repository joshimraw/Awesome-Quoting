<template>
<div class="container">
	<div class="row justify-content-center">
		<div class="col-5">
			<h2 class="text-info">Http with Firebase</h2>
			<div class="form-group">
				<label>User Name</label>
				<input type="text" class="form-control" v-model="users.name">
			</div>

			<div class="form-group">
				<label>Email Address</label>
				<input type="text" class="form-control" v-model="users.email">
			</div>
			<button class="btn btn-primary" @click="submit">Submit</button>
		</div>
	</div>
</div>
</template>

<script>
	export default{
		data(){
			return {
				users: {
					name: '',
					email: ''
				}
			}
		},
		methods: {
			submit(){
				this.$http.post('https://vuejs-http-ae6c8.firebaseio.com/data.json', this.users)
				.then(response => {
					console.log(response);
				}, error => {
					console.log(error);
				});
			}
		}
	}
</script>