<template>
	<div v-if="jobData">
		<h1>{{ jobData.title }}</h1>
		<p>The job id is {{ jobData.id }}</p>
		<p>The job details are {{ jobData.details }}</p>
	</div>

	<div v-else>
		Loading jobs...
	</div>

</template>

<script>
export default {
	props: ['id'],
	data() {
		return {
			jobData: null,
		}
	},
	mounted() {
		fetch(`http://localhost:3000/jobs/${this.id}`)
			.then(res => res.json())
			.then(data => this.jobData = data)
			.catch(error => console.log(error.message))
	}
}
</script>

<style>

</style>
