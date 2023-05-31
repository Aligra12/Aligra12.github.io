<h1>Floorball and more</h1>  <!-- Rubrik -->

<script>
     import "prism-themes/themes/prism-one-dark.css"; /*kan ta bort sen denna är med till länken längs ner i dokumentet nav..*/
    import { query_selector_all } from "svelte/internal";
	let cart = []; /*lista med alla produkter, namn, pris men även bildlänk och id*/
	let products = [
		{id: 1, name: "Innebandyklubba", adress:"/klubba1", image: "https://media.viskan.com/v2/klubbhusetprod/list/OXD-52310058_Bleached%20Red-Black_1_Oxdog%20Innebandyklubba%20Hyperlight%20HES%2027%20-%20OptiLight%2023-24.jpg", price: 1800, quantity: 1}, //kostnaden // dock så syns inget utav namnen just nu men det gör inget ännu 3 maj // löste problemet det var att färgen för texten var vit och syntes inte.
        {id: 2, name: "Innebandyklubba", adress:"/klubba2", image: "https://media.viskan.com/v2/klubbhusetprod/original/OXD-52310114_White-Gold_1_Oxdog%20Innebandyklubba%20Ultralight%20HES%2027%20-%20FSL%2023-24.jpg", price: 1600, quantity: 1},  
        {id: 3, name: "Innebandyklubba", adress:"/klubba3", image: "https://media.viskan.com/v2/klubbhusetprod/normal/OXD-52219468-OL_Ultra%20Violet_1_Oxdog%20Innebandyklubba%20UltraLight%20HES%2027%20SMU%20-%20OptiLight.jpg", price: 1800, quantity: 1}, //kostnaden // dock så syns inget utav namnen just nu men det gör inget ännu 3 maj // löste problemet det var att färgen för texten var vit och syntes inte.
        {id: 4, name: "Innebandyboll", adress:"/boll1",image: "https://media.viskan.com/v2/klubbhusetprod/original/SAL-4131891_Lime%20Green_1_Salming%20Innebandyboll%20AERO-NEW2022.jpg", price: 50, quantity: 1}, //kostnaden // dock så syns inget utav namnen just nu men det gör inget ännu 3 maj // löste problemet det var att färgen för texten var vit och syntes inte.
        {id: 5, name: "Innebandyboll", adress:"/boll2", image: "https://media.viskan.com/v2/klubbhusetprod/original/KH184004_Rosa_1_KH%20Innebandyboll%20Official%20SSL%20Ball-NEW.jpg", price: 50, quantity: 1}, //kostnaden // dock så syns inget utav namnen just nu men det gör inget ännu 3 maj // löste problemet det var att färgen för texten var vit och syntes inte.
        {id: 6, name: "Innebandyboll", adress:"/boll3",image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTl33_bBHfo_Wx8kqhPGOiGYZNHIfWVgPTcIs06o13lvdpLdiEx9uKyL4gpqatJGGpbLjg&usqp=CAU", price: 50, quantity: 1}, //kostnaden // dock så syns inget utav namnen just nu men det gör inget ännu 3 maj // löste problemet det var att färgen för texten var vit och syntes inte.
        {id: 7, name: "grepplinda", adress:"/linda1",image: "https://media.viskan.com/v2/klubbhusetprod/original/KH165001-1_Gr%C3%A5_1_KH%20Overgrip.jpg", price: 150, quantity: 1}, //kostnaden // dock så syns inget utav namnen just nu men det gör inget ännu 3 maj // löste problemet det var att färgen för texten var vit och syntes inte.
        {id: 8, name: "grepplinda", adress:"/linda2",image: "https://media.viskan.com/v2/klubbhusetprod/original/KH165001-1_Vit_1_KH%20Overgrip.jpg", price: 150, quantity: 1}, //kostnaden // dock så syns inget utav namnen just nu men det gör inget ännu 3 maj // löste problemet det var att färgen för texten var vit och syntes inte.
        {id: 9, name: "grepplinda", adress:"/linda3", image: "https://media.viskan.com/v2/klubbhusetprod/original/KH165001-1_Svart_1_KH%20Overgrip.jpg", price: 150, quantity: 1}, //kostnaden // dock så syns inget utav namnen just nu men det gör inget ännu 3 maj // löste problemet det var att färgen för texten var vit och syntes inte.
        
	] /*input namn personupgifter*/
	let adress = {
		namn: "",
		email:"",
		telefonnummer:"",
		adress:"",
		stad:"",
		stat:"",
		pin:"",

	}                     /*pushar till varukorgen*/
    const addToCart = (product) => {   /*quantity är 1 så när man klickar på plus knappen så läggs en vara till*/
		for(let item of cart) {
				if(item.id === product.id) {  /*kollar om id för item är samma som produkt om det stämmer +1*/
					product.quantity += 1       /*genom att i listan längst upp att jag gav de ett id så blir det lätt*/
					cart = cart;
					return;  /*retunerar */
				}
		}
		cart = [...cart, product]
	}
	
	const minusItem = (product) => {   /*samma som ovan bara att när du klickar på minusknappen så tar den bort en produkt*/
		for(let item of cart) {
				if(item.id === product.id) {
					if(product.quantity > 1 ) {
							product.quantity -= 1
							cart = cart
					} else {
							cart = cart.filter((cartItem) => cartItem != product)
					}
					return;
				}
		}
	}
	
	const plusItem = (product) => {
		for(let item of cart) {
			if(item.id === product.id) {
				item.quantity += 1
				cart = cart;
				return;
			}
		}
	}

	$: total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0) /*tar summan och produkterna*/

	const checkOut = ()=>{
		alert(JSON.stringify(cart))   /*skickar ut ett medelande när man klickar på betala så komemr antalet produkter upp som en notis*/
		alert(JSON.stringify(adress)) /*skickar ut ett medelande fast med all din personliga information*/
		

	}
	

</script>

<!--<a class= "klubba1" href="/klubba1"><img src="https://media.viskan.com/v2/klubbhusetprod/list/OXD-52310058_Bleached%20Red-Black_1_Oxdog%20Innebandyklubba%20Hyperlight%20HES%2027%20-%20OptiLight%2023-24.jpg" alt=klubba1 width="263" height="100"></a>-->

<div class="product-list">  <!--mina produkters lista-->
	
	{#each products as product}
	<div>
		<a href={product.adress} ><div class="image" style="background-image: url({product.image})"></div></a>  <!--länkar bilderna till en ny sida-->
		
	<h4>{product.name}</h4> <!--namn -->  
	<p>{product.price}kr/st</p>  <!--Lägger till priset och namn-->
	<button on:click={() => addToCart(product)}>Lägg till i Varukorgen</button> <!--lägger till varukorgs knapparna som sedan läggs till i varukorgen då man klickar på knappen-->
	</div> 
	{/each}
</div>

<div class="cart-list">  <!--ny lista för kundvagn-->
	<!--loop-->
	{#each cart as item }
		{#if item.quantity > 0}
		<div class="cart-item"> 
			<img width="50" src={item.image} alt={item.name}/>  <!--bild bredd och namn-->
			<div>{item.quantity}  <!--antalet produkter-->
				<button on:click={() => plusItem(item)}>+</button> <!--adderar produkter -->
				<button on:click={() => minusItem(item)}>-</button> <!--subtraherar produkter-->
			</div>
			<p>{item.price * item.quantity}kr</p> <!-- tar priset på produkten och multiplicerar det med antalet produkter-->
		</div>
		{/if}
	{/each}
	<div class="total">
		<h4>Totalt:{total} kr</h4>
	</div>
</div>


<p>Du har {cart.length} produkter i din varukorg</p>
<div class="shipping-adress">  <!--personuppgifter class-->
	<div>        <!---Kontaktuppgifter nedan-->
	<p>Namn</p>
	<input bind:value={adress.namn}/> <!--kopplar genom binda till p labels / till let adress{}... -->

	<p>Email</p>
	<input bind:value={adress.email}/> 
	
	<p>Telefonnummer</p>
	<input bind:value={adress.telefonnummer}/> 
	
	<p>Adress</p>
	<textarea bind:value={adress.adress} cols="24" rows="6"></textarea> 

	<p>Stad</p>
	<input bind:value={adress.stad} />

	<p>Stat</p>
	<input bind:value={adress.stat}/>

	<p>PIN</p>
	<input bind:value={adress.pin} />

	<div>
		<button on:click={checkOut}>Betala</button>   <!--knapp som sen leds till const checkOut... skickar ut ett meddeland med vad man köpt och sina personupgifter-->
	</div>
	

	</div>
	<div class = "current-adress">  
		<p>{adress.namn}</p>
		<p>{adress.email}</p>
		<p>{adress.telefonnummer}</p>
		<p>{adress.adress}</p>
		<p>{adress.stad}</p>
		<p>{adress.stat}</p>
		<p>{adress.pin}</p>
	</div>
</div>
<style>
	.product-list, .cart-item {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
	}
	
	.image {
		height: 350px;
		width: 350px;
		background-size: contain;
		background-position: center;
		background-repeat: no-repeat;
        
       
	}
	.total {
		text-align: right;
        width:max-content;
		margin-right:42px;
        
        
	}
	
	.cart-list {
		border: 3px solid;
        border-color: rgb(0, 0, 0);
		padding: 8px;
        width: max-content;
        margin-left: 42px;
		
	}
	.shipping-adress{
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 1em;

		
}
	.current-adress{
		padding: 2em;	
		border: 2px dashed blue;
		background-color: rgba(216, 220, 219, 0.219);
	}
     h4 {
        color: rgb(0, 0, 0);
        font-family:'Times New Roman', Times, serif, cursive; /*stylar Total*/
		font-size: 1em;
        font-size: x-large;
        margin-left: 42px;
        

    }
     button {
        font-family:'Times New Roman', Times, serif, cursive; /*stylar Total*/
		font-size: 1em;
        width: max-content;   /* gör så att button blir midre*/
        background-color: rgb(10, 0, 0);
        margin-left: 42px;
        
	
    }
     p{
        font-family:'Times New Roman', Times, serif, cursive; /*stylar Total*/
		font-size: large;
        color: rgb(10, 3, 0);
        margin-left: 42px;
	

        

    }
     h1{
        font-family:fantasy, cursive; /*stylar Total*/
		font-size: 2em; 
        color: rgb(255, 255, 255);
        text-align: center;
        background-color: black;
        padding: 10px;

     }
  
     nav {
      margin-left: 3%;
      margin-right: 15%;
      
    }
	
	 .klubba1{
		margin-left: 44px;
		margin-bottom: 200px;
		
	
	}
	


	
</style>
