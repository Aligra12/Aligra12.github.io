<h2> KH Innebandyboll Official SSL Ball </h2>


<div>
  <div class="carousel">
    <ul class="slides">
      <input type="radio" name="radio-buttons" id="img-1" checked />
      <li class="slide-container">
        <div class="slide-image">
          <img src="https://media.viskan.com/v2/klubbhusetprod/original/KH184004_Rosa_1_KH%20Innebandyboll%20Official%20SSL%20Ball-NEW.jpg">
        </div>
        <div class="carousel-controls">
          <label for="img-3" class="prev-slide">
            <span>&lsaquo;</span>
          </label>
          <label for="img-2" class="next-slide">
            <span>&rsaquo;</span> 
          </label>
        </div>
      </li>
      <input type="radio" name="radio-buttons" id="img-2" />
      <li class="slide-container">
        <div class="slide-image">
          <img src="https://media.viskan.com/v2/klubbhusetprod/original/KH184004_Rosa_2_KH%20Innebandyboll%20Official%20SSL%20Ball-NEW.jpg">
        </div>
        <div class="carousel-controls">
          <label for="img-1" class="prev-slide">
            <span>&lsaquo;</span>
          </label>
          <label for="img-3" class="next-slide">
            <span>&rsaquo;</span>
          </label>
        </div>
      </li>
      <input type="radio" name="radio-buttons" id="img-3" />
      <li class="slide-container">
        <div class="slide-image">
          <img src="https://media.viskan.com/v2/klubbhusetprod/original/KH184004-3_Rosa_1_KH%20Official%20SSL%20Ball%20(3-pack).jpg">
        </div>
        <div class="carousel-controls">
          <label for="img-2" class="prev-slide">
            <span>&lsaquo;</span>
          </label>
          <label for="img-1" class="next-slide">
            <span>&rsaquo;</span>
          </label>
        </div>
      </li>
      <div class="carousel-dots">
        <label for="img-1" class="carousel-dot" id="img-dot-1"></label>
        <label for="img-2" class="carousel-dot" id="img-dot-2"></label>
        <label for="img-3" class="carousel-dot" id="img-dot-3"></label>
      </div>
    </ul>
  </div>
  <p>Varumärke: KH</p>
  <p>Artikelnummer: 
    KH184004</p>


   
   
  
    <p>Vi på Floorball and more är otroligt stolta över att vår boll är den officiella SSL-bollen, som används vid matchspel i SSL för både damer och herrar.
        Till säsongen 23/24 uppdateras bollen med en ny officiell färg, som är något unik. Bollen är neongul och sticker ut på ett annat sätt än vad den förra officiella färgen Aprikos gör.
        </p>

</div>

<style>

  .carousel {
    margin-left: 25%; /*placering bild i mitten x*/
    margin-right: 15%;
}

ul.slides {
    display: block;
    position: relative;
    height: 600px;
    margin: 0;
    padding: 0;
    overflow: hidden;
    list-style: none;
}

.slides * {
    user-select: none;
    -ms-user-select: none;
    -moz-user-select: none;
    -khtml-user-select: none;
    -webkit-user-select: none;
    -webkit-touch-callout: none;
}

ul.slides input {
    display: none; 
}


.slide-container { 
    display: block; 
}

.slide-image {
    display: block;
    position: absolute;
    width: 100%;
    height: 150%;
    top: 0;
    opacity: 0;
    transition: all .7s ease-in-out;  /*hur snabbt den ska byta bild*/
}   

.slide-image img {
    width: auto;
    min-width: 70%;
    height: 80%;
}

.carousel-controls {
    position: absolute;
    top: 0;
    left: 0;  /*kontroll vänster x led*/
    right: 130px;/*kontroll vänster x led*/
    
    z-index: 999;
    font-size: 100px;
    line-height: 600px;
    color: rgb(255, 255, 255);
}

.carousel-controls label {
    display: none;
    position: absolute;
    padding:0 20px;
    opacity: 0;
    transition: opacity .2s; /*snabbt pilen kommer fram då man står med musen över*/
    cursor: pointer;
}

.slide-image:hover + .carousel-controls label{
    opacity: 0.5;
}

.carousel-controls label:hover {
    opacity: 1;
}

.carousel-controls .prev-slide {
    width: 49%;
    text-align: left;
    left: 0;
}

.carousel-controls .next-slide {
    width: 49%;
    text-align: right;
    right: 0;
}

.carousel-dots {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 20px;
    z-index: 999;
    text-align: center;
}

.carousel-dots .carousel-dot {
    display: inline-block;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background-color: #fff;
    opacity: 0.5;
    margin: 10px;
}

input:checked + .slide-container .slide-image {
    opacity: 1;
    transform: scale(1);
    transition: opacity 1s ease-in-out;
}

input:checked + .slide-container .carousel-controls label {
     display: block; 
}

input#img-1:checked ~ .carousel-dots label#img-dot-1,
input#img-2:checked ~ .carousel-dots label#img-dot-2,
input#img-3:checked ~ .carousel-dots label#img-dot-3,
input#img-4:checked ~ .carousel-dots label#img-dot-4,
input#img-5:checked ~ .carousel-dots label#img-dot-5,
input#img-6:checked ~ .carousel-dots label#img-dot-6 {
	opacity: 1;
}


input:checked + .slide-container .nav label { display: block; }
h2{
  color: black;
  text-align: center;

}
p{
 color: black;
 margin-top: 60px;
}
</style>