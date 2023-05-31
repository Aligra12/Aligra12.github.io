<script>
	
    let newItem = '';
	
    let todoList = [
                    
                    ];
	
	function addToList() {
		todoList = [...todoList, {text: newItem, status: false}];
		newItem = '';
	}
	
	function removeFromList(index) {
		todoList.splice(index, 1)
		todoList = todoList;
		function clear() {
		todos = todos.filter(t => !t.done);
	}
    }
</script>
<div>
	<img alt="Flower" src="https://i.pinimg.com/originals/66/fa/b5/66fab57f59169ac19231c72f6e18d846.png" />
	
	<p>TODO-</p><p2>LIST</p2>


</div>

<div>
<img2 alt="Flower" src="https://i.pinimg.com/originals/66/fa/b5/66fab57f59169ac19231c72f6e18d846.png" />
</div>

<input class="input" bind:value={newItem} type="text" placeholder="Vad ska du göra?..">
<button class="Add" on:click={addToList}>Add</button>

<br/>
{#each todoList as item, index}
	<input class="box" bind:checked={item.status} type="checkbox">
	<span class:checked={item.status}>{item.text}</span>
	<span on:click={() => removeFromList(index)}>💜</span>
	<br/>
{/each} 


<style> 
	.checked {
        text-decoration: line-through;
    }
	p {
		color: rgb(130, 13, 130);
		font-family: 'Comic Sans MS', cursive;
		font-size: 3em;
		margin-bottom:8%;
		margin-left:30%;
		
	}
	p2{
		color: rgb(130, 13, 130);
		font-family: 'Comic Sans MS', cursive;
		font-size: 3em;
		margin-bottom:40%;
		margin-left:1%;
		
	}
	.Add {
		color: rgb(130, 13, 130);
		background-color: rgb(152, 121, 182);
		width: min-content;
		
	}
	.box{
		background-color: rgb(152, 121, 182);
	}
	.input{
		background-color: rgb(234, 227, 240);
		color: rgb(138, 35, 138);
		width: min-content;
	}
	
	div {
	width: 40vw;
	  display: flex;
	  flex-direction: row;
	  background-position: 20%;
	  margin-right: 60%;
	  margin-top: 10px;
	  justify-content: space-between ;	
	  justify-content: space-evenly ;
	 

	}
  
	img {
	  width: 750px;

	}
	img {
	  width: 750px;
	  
	}
 :global(body){
        background-color: rgb(236, 214, 253);
       
    }
</style> 

