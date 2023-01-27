<script>
  import "@picocss/pico"

  let clicks = 100;
  let multiplier = 1;
  let workers = [];
  let worker_multiplier = 1;
  let bg = null;
  let max = 200;

  let upgrades = [
    { cost: 50, name: "~Doubler~", multiplier: 2, worker: 0 },
    { cost: 10, name: "~Worker~", multiplier: 0, worker: 1 },
  ];
  // sleep time expects milliseconds
  function sleep (time) {
    return new Promise((resolve) => setTimeout(resolve, time));
  }

  function increment() {
    clicks = clicks + multiplier;
    console.log("click" + clicks);
    bg = `url("https://i.pinimg.com/originals/c7/d2/9f/c7d29f06ce5087d5317ea9b6ce2e8f8f.gif")`;
    sleep(1000).then(()=>{
        bg = null;
    });

    if (clicks > max) {
      max = max * 2
      clicks = 0 
    }
   
  }
  
  import AudioPlayer, { stopAll } from './AudioPlayer.svelte'

  let audioTracks = [
    'https://sveltejs.github.io/assets/music/strauss.mp3',
  ]

 
	import MovingDiv from './MovingDiv.svelte';
  
</script>



<h1 class= "top"> Välkommen till Alice Granlunds hemsida!</h1> 
<h1 class= "top"> Galaxy</h1> 
<p class= "top">Få så många poäng som möjligt genom att klicka på den runda "cirkeln"
  och skaffa fler workers. Du kan även dubblera värdet på clicksen genom 
  att betala medhjälp av dina poäng från clicksen.
</p> 






<article>
  
  <progress value={clicks} max ={max}></progress>
<div class="Stop"></div>

  <button on:click={stopAll}>
    Pausa musiken
  </button>
  {#each audioTracks as src}
  <AudioPlayer {src} />
{/each}

  <header>
  
    
    <div class="grid">
      {#each upgrades as upgrade}
        <button
          class="upgrade"
          on:click={() => {
            if (clicks >= upgrade.cost) {
              if (upgrade.multiplier) {
                multiplier = multiplier * upgrade.multiplier;
                clicks -= upgrade.cost;
              }
              if (upgrade.worker && clicks) {
                worker_multiplier = worker_multiplier * 2;
                workers = [upgrade.name, ...workers];
                /* start "clicking" every 1000 ms */
                setInterval(increment, 1000);
                clicks -= upgrade.cost;
              }
              upgrade.cost*=2
            } else {
              alert("Du har för lite poäng, klicka mer!");
            }
          }}
        >
          <span>{upgrade.name}</span>
          <span>{upgrade.cost }</span>
        </button>
      {/each}
    </div>
  </header>
  <MovingDiv class="movdiv">
    <img alt ="spaceship" src = "https://static.vecteezy.com/system/resources/previews/008/851/131/original/3d-icon-illustration-space-rocket-png.png"/>
  </MovingDiv>
  
  <div class="game" style="background-image:{bg}">
    <button on:click={increment} class="clicker">
      <span class="clicks">{clicks}</span>
        
      <span class="pointtext">PPC: {multiplier}</span>
    </button>
  </div>
  <footer>
    <div class="panelright">
      <div>
        <span>Workers</span>
        <hr />
        <div class="shop">
          {#each workers as worker}
            <div class="worker">{worker}</div>
          {/each}
        </div>
      </div>
      <hr />
    </div>
  </footer>
</article>


<style>
  
  	/* Bigger margin */
	:global(.moving-div) {
		padding: 2rem 5rem
	}
	
	/* Custom transition speed */
	:global(.moving-div > .inner-div) {
		transition: transform .25s!important
	}
  
  .top{
    color: rgb(67, 6, 100);
    margin-bottom: 0;

  
  }

  .shop {
    display: grid;
    grid-auto-flow: row; /* default */
    gap: 8px;
    grid-template-rows: repeat(3, 1fr);
    grid-template-columns: repeat(3, 1fr);
  }

  .upgrade {
    width: 100%;
    height: 100%;
    border: 4px solid rgb(48, 17, 75);
    
    background-size: cover;
    background-image: url("https://cdn5.vectorstock.com/i/1000x1000/14/14/dark-night-sky-with-stars-and-galaxy-vector-21501414.jpg");
    place-items: center;
    place-content: center;
    display: flex;
    flex-direction: column;
    
  }

  .worker {
    width: 100%;
    height: 100%;
    border: 1px solid rgb(40, 22, 68);
    background-color: rgb(7, 7, 7);
    place-items: center;
    place-content: center;
    display: flex;       
  }

  .game {
    height: 50vh;
    display: flex;
    flex-direction: column;
    place-items: center;
    place-content: center;
    background-size: cover;
    background-color: black;
   
  }
  .clicker {
    clip-path: circle();
    display: flex;
    height: 100%;
    width: 100%;
    flex-direction: column;
    place-items: center;
    place-content: center;
    background-image: url("https://rare-gallery.com/uploads/posts/4547975-astronaut-stars-fantasy-art.jpg");
    background-size: cover;
    background-position: 0px -100px;
  }

  .panelright {
    height: 100%;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .clicks {
    font-size: 100px;
  }

  .pointtext {
    color: rgb(255, 255, 255);
    font-size: 25px;
    font-weight: bold;
  }

  .Stop {
    width: 100%;
    height: 100%;
    border: 15px solid rgb(40, 22, 68);
    background-color: rgb(7, 7, 7);
    place-items: center;
    place-content: center;
    display: flex;       
  }

  progress{
  background-color:blueviolet;
  scrollbar-color: black;
}

progress[value]::-webkit-progress-value {
  background-color: rgb(49, 4, 70);
    

    border-radius: 2px; 
    background-size: 35px 20px, 100% 100%, 100% 100%;
}



</style>


