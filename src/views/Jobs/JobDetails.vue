<template>
	<h1>Job details page</h1>
	<p>The job id in {{ id }}</p>
</template>

<script>
export default {
	data() {
		return {
			id: this.$route.params.id
		}
	},
}
</script>

<style>

</style>
