<script setup>
$(document).ready(function(){ 
    const cryingCat = 'https://i.pinimg.com/originals/18/1c/06/181c065b666891b204e8d7f2ee4e7111.gif'
    const btnNo = $(`#btnNo`)
    const btnYes = $(`#btnYes`)
    const cat = $(`#cat`)
    function getRandomInt(min, max) {
        min = Math.ceil(min);
        max = Math.floor(max);
        return Math.floor(Math.random() * (max - min) + min);
    }

    function btnTeleport() {
        let random = getRandomInt(-600,600)
        let randomSec = getRandomInt(-600,600)
        btnNo.css({
            'left': random + 'px',
            'right': random  + 'px',
            'top' : randomSec  + 'px',
            'bottom' : randomSec + 'px',
        })
        cat.attr('src', cryingCat)
    }

    btnNo.mouseenter(() => {
        btnTeleport()
    })
    btnNo.click(() =>{
        btnTeleport()
    })
    
    btnYes.click(() => {
        cat.attr('src','https://media3.giphy.com/avatars/nekousa_1110/Wm3uOmYzgnNS.gif')
        btnNo.css('display', 'none')
    })
})
</script>

<template>
  <div class="middle">
    <br>
    <h1>Will you marry me?</h1>
    <img id="cat" src="https://i.pinimg.com/originals/15/0f/78/150f78d18fd597611f77b4ae7d2f1f58.gif"> 
    <div class="buttons">
        <button id="btnYes"> Yes</button>
        <button id="btnNo" style="margin-left: 90px ;"> No</button>
    </div>
</div>
</template>

<style scoped>
.middle img{
  position: relative;
  left: 40%;
  height: 500px;
}


#cry {
  display: none;
}
.middle h1 {
  text-align: center;
  font-family: beer;
  font-size: 45pt;
}


.buttons {
  height: 200px;
  width: 300px;
  position: relative;
  left: 44%;
  padding-top: 50px;
}

.buttons button {
  position: relative;
  background-color: #272727;
  border: none;
  color: white;
  padding: 20px 37px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  border-radius: 15px;
  cursor: pointer;
  transition: 1s;
  font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

.buttons button:hover {
  scale: 1.1;
}


</style>
