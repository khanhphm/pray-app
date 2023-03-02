<template>
  <div id="app">
    <div id="header">
      THẮP HƯƠNG ONLINE
    </div>
    <div id="main">
      <div id="imga">
        <div>
          <img id="pray" src="./assets/image.png" alt="#">
        </div>
        <img v-if="smoke" id="smoke" src="./assets/smoke.gif" alt="">
      </div>
      <div id="tex">
        <textarea v-model="message" placeholder="Viết lời cầu nguyện..." cols="30" rows="5"></textarea>
      </div>

      <button v-on:click="pray()">
        Thắp hương
      </button>
    </div>
  </div>
</template>

<script>


export default {
  data()
  {
    return {
      smoke: false,
      message: '',
      audio: new Audio('/audio.mp3')
    };
  },
  methods: {
    pray()
    {
      console.log(this.message);
      if (this.message.length > 0)
      {
        console.log(this.message);
        this.smoke = true;
        this.audio.play();
        this.message=""
      } 
    }
  },
  mounted(){
    this.audio = new Audio('/audio.mp3');
  }

}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  background-color: #F4FAD8;

  letter-spacing: 0.11em;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

}

#header {
  text-align: center;
  padding: 16px;
  background-color: #D62121;
  font-family: 'Inter';
  font-style: normal;
  font-weight: 900;
  font-size: 24px;
  letter-spacing: 0.11em;
  color: #FDC000;

  text-shadow: 0px 2px 2px rgba(153, 153, 153, 0.25);
}

#imga {
  margin-top: 220px;
}

#tex {
  margin-top: 60px;
}

#pray {
  width: 280px;
  height: 150px;
}

textarea {
  border: 3px solid #602911;
  border-radius: 7px;
  background-color: #fff;
  padding: 10px;
  font-family: Inter;
  font-style: normal;
  font-weight: 900;
  font-size: 11px;
  line-height: 13px;
  color: rgba(96, 41, 17, 0.4);



}

button {
  margin-top: 40px;
  font-weight: 900;
  font-size: 12px;
  line-height: 15px;
  box-sizing: border-box;
  font-family: Inter;
  background: #FDC000;
  border: 2px solid #602911;
  border-radius: 8px;

  padding: 6px 8px;
}

#smoke {
  position: absolute;
  top: 176px;
  left: 50%;
  transform: translate(-50%, 0%);
  background-color: rgba(0, 0, 0, 0);
  width: 250px;
  opacity: 0.3;
}</style>
