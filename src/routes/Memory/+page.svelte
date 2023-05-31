<h3 class=memory>Memory</h3>
<script>

    let cards = [];
    let random= Math.random()*(200);
    let round=Math.round(random);
    let sets = 4;
    for (let index = 0; index < sets*2; index++) {
        
        
        cards.push({
        
        id: index, // TODO: unique ids per card card
        img: "https://picsum.photos/id/"+(round+index%sets).toString()+"/200/300", // TODO: unique images per card card
        flipped: false,  // TODO: think
        completed: false,
      });
    }
    cards = cards.sort(() => Math.random() - 0.5)

    let flipcount = 0;
    function flip(card) {
        card.flipped = true;
        flipcount ++;
        
      // flip card over if two cards are not already flipped
      // TODO: and card is already not flipped
        console.log(flipcount)
        
        
        

        
      if (card.flipped && flipcount <= 2 ) {
       
        // TODO: Probably do what?
        // flip the cards over after 2s from seeing both cards
        if (flipcount == 2) {
            cards.forEach((card2)=> { 
                if (card.img==card2.img && card2.flipped && card.id != card2.id){
                    card2.completed=true;
                    card.completed=true;
                }
            }); 
            
          setTimeout(() => {
            
            // flip over cards that have not been marked as "completed"
            cards.forEach((card) => {
              card.flipped = card.completed;
              

            });
            flipcount = 0;
            cards = cards;
          }, 1000);
        }
        cards = cards;
        
      } else {
        alert("vänta ett litet tag till");
      }
      
    }
  </script>
  
  <main>
    <div class="row">
      {#each cards as card, i}
        <div
          on:click={() => {
            flip(card);
          }}
          on:keypress={() => {
            flip(card);
          }}
          class:flipped={card.flipped}
          class="card"
        >
          <img class="front" src={card.img} alt="" />
          <img class="back" src="data:image/jpeg;base64,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" alt="" />
        </div>
      {/each}
    </div>
  </main>
  
  <style>
    main {
      margin-top: 50px;
      display: flex;
      place-content: center;
      place-items: center;
    }
    .memory{
        background-color: rgb(163, 150, 231);
    }
    .row {
      display: grid;
      gap: 20px;
      grid-template-columns: repeat(3, 100px);
      grid-template-rows: repeat(3, 100px);
    }
    .card {
      border: 1px solid rgb(228, 52, 25);
      cursor: pointer;
      transition: transform 1s;
      transform-style: preserve-3d;
      width: 100%;
      height: 100%;
    }
    .card.flipped {
      transform: rotateY(180deg);
    }
    .card .back {
      transform: rotateY(0deg);
    }
    .card .front {
      transform: rotateY(180deg);
    }
    .card img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      backface-visibility: hidden;
      -webkit-backface-visibility: hidden;
      position: absolute;
    }
  </style>