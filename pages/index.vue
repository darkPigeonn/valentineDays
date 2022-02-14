<template>
 <div class="relative flex items-top justify-center min-h-screen bg-gray-100 sm:items-center sm:pt-0" style="background-image : url(aasa.jpeg);background-blend-mode: overlay;background-size: cover;background-position-y: center;">

  <div class="d-flex flex-column">

       <h1 class="text-xs-h1" style="font-family: candy; display: block;font-weight: 300;font-size: 80px;color: red;letter-spacing: 1px;" > Hai Nyong! </h1> <br>
       <img id="img1" src = "https://c.tenor.com/Z8ezUHZzcLoAAAAC/love.gif" style=" visibility: hidden;">

       <h3 class="text-xs-h1" style="font-family: candy; display: block;font-size: 40px;color: red;letter-spacing: 1px;" > Maukah kamu menjadi pacarku?? </h3>
      <v-button  id ="btn_mau" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="mau()"> Mau </v-button>
      <button id="btn_gak" class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded" style="position : relative" @click="gamau(this)" > Gamau </button>
    <p>~ Kasih itu murah hati, kasih itu percaya ~</p>
  <!-- <v-carousel
    cycle
    height="50%"
    :show-arrows = "false"
  >
    <v-carousel-item
     v-for="(item,i) in items"
      :key="i"
      :src="item.src"
      reverse-transition="fade-transition"
      transition="fade-transition"
    >

    </v-carousel-item>
  </v-carousel> -->
  </div>
    <audio autoplay controls hidden>
       <source src="sss.mp3" type="audio/mpeg">
    </audio>


 </div>


</template>

<script>

export default {
  name: 'IndexPage',
data () {
      return {
        items: [
          {
            src: '/noo/1.jpeg',
          },
          {
            src: '/noo/2.jpeg',
          },
          {
            src: '/noo/3.jpeg',
          },
          {
            src: '/noo/4.jpeg',
          },
        ],
      }
    },
  mounted() {
  
    this.start()
    this.love()

    setInterval(()=> {
      this.stop()
    },15000)
  },
   methods: {
     mau(){
       const imgg = document.getElementById("img1");
       imgg.style.visibility = "visible"
       alert("Ego Amote Sayang!")
     },
     gamau (id){
      //  const mau = document.getElementById("btn_mau");
       const gamau =document.getElementById("btn_gak");
      const i = Math.floor(Math.random() *5) +1 ;
      const j = Math.floor(Math.random() *5) +70;
      gamau.style.left = i + "px";
      gamau.style.top = j + "px";
     },
      start() {
        this.$confetti.start();
      },
     stop() {
        this.$confetti.stop();
      },
      love() {
        this.$confetti.update({
          particles: [
            {
              type: 'heart',
            },
            {
              type: 'circle',
            },
          ],
          defaultColors: [
            'red',
            'pink',
            '#ba0000'
          ],
        });
      }
   }
}
</script>

<style scoped>
.wrapper {
  height: 100vh;
  /*This part is important for centering*/
  display: flex;
  align-items: center;
  justify-content: center;
}

.typing-demo {
  width: 22ch;
  animation: typing 2s steps(50), blink .5s step-end infinite alternate;
  white-space: nowrap;
  overflow: hidden;
  border-right: 3px solid;
  font-family: monospace;
  font-size: 2em;
}

@keyframes typing {
  from {
    width: 0
  }
}

@keyframes blink {
  50% {
    border-color: transparent
  }
}
</style>
