<template>
 <div class="relative flex items-top justify-center min-h-screen bg-gray-100 sm:items-center sm:pt-0" style="background-image : url(aasa.jpeg);background-blend-mode: overlay;
    background-size: cover;
    background-position-y: center;">
    
  <div class="d-flex flex-column">
  
       <h1 class="text-xs-h1" style="font-family: candy;
    display: block;
    font-weight: 300;
    font-size: 80px;
    color: red;
    letter-spacing: 1px;" > Happy Valentine Day Nyong </h1> <br>
    <p>~ Kasih itu murah hati, kasih itu percaya ~</p>
  
  </div>

 </div>
 
</template>

<script>

export default {
  name: 'IndexPage',
  mounted() {
    this.sound()
    this.start()
    this.love()

    setInterval(()=> {
      this.stop()
    },8000)
  },
   methods: {
     sound() {
        new Audio('sss.mp3').play();
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