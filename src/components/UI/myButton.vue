<template>
	<button class = 'btn'>
		<slot></slot>
	</button>
	
</template>

<script>
	export default{
		name: 'my-button'	
	}
	
</script>


<style scoped>
.btn{
    cursor: pointer;
    color: white;
    border: none;
    padding: 15px 18px;
  }
	
</style>