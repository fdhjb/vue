<template>
  <div>
  	<div>
	    <input v-model="inputValue"/>
	    <button @click="handleSubmit">add to TodoList</button>
    </div>
    <ul>
    	<todo-item 
    		v-for="(item,index) of List" 
    		:key="index" 
    		:content="item" 
    		:index="index"
    		@delete="fatherCDelete">
    	</todo-item>
    </ul>
  </div>
</template>

<script>

	import TodoList from './components/TodoItem.vue'
	export default {
		components:{
			'todo-item':TodoList
		},
		data(){
	  		return {
	  			inputValue:'',
	  			List:[]
	  		}
	},
	methods:{
	  	handleSubmit(){
	  		if(this.inputValue == ''){
	  			alert("you should type something...")
	  		}else{
	  			this.List.push(this.inputValue)
	  			this.inputValue = ''
	  		}
	  		 
	  	},
	  	fatherCDelete(index){
	  		this.List.splice(index,1)
	  	}
	}
}
</script>

<style>

</style>
