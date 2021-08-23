<template>
   <h1>Ask Me!</h1>
  <img v-if="img" :src="img" alt="bg">
  <div class="bg-dark"></div>

  <div class="indecision-container">
      <input 
      v-model="question"
      type="text" 
      placeholder="ask me something ❤">
      <p>do not forget to put the question mark at the end (❓)</p>
      <div v-if="isValidQuestion">
          <h2> {{question}} </h2>
          <h1> {{answer === 'yes' ? 'Yes ✅' : 'No ❌'}} </h1> 
      </div>
     
  </div>
    <div class="footer">
            <Footer />
           
    </div>

</template>

<script>
import Footer from './Footer.vue'


export default {
  components: { Footer },

    data(){
        return{
            question:null,
            answer:null,
            img:null,
            isValidQuestion:false,
        }
       
    },
    methods:{
        async getAnswer(){
        this.answer = 'thinking 🤔'

          const {answer,image} = await fetch('https://yesno.wtf/api').then(resp => resp.json() )

          this.answer = answer
          this.img = image
        }
    },
     watch: {
            question(value,oldValue){
                this.isValidQuestion = false
                if(!value.includes('?')) return
                this.isValidQuestion = true
                this.getAnswer()
                //TODO 'http peticion'
            }
        }

}
</script>

<style>
    .footer{
    margin-top: 300px;
  
  }

    img, .bg-dark {
        height: 100vh;
        left: 0px;
        max-height: 100%;
        max-width: 100%;
        position: fixed;
        top: 0px;
        width: 100vw;
    }

    .bg-dark {
    background: linear-gradient(
    to left,
    rgba(7,27,82,0.2) 0%,
    rgba(0,128,128,0.2) 100%
  );
    }

    .indecision-container {
        position: relative;
        z-index: 99;
    }
    
    input {
        width: 250px;
        padding: 10px 15px;
        border-radius: 5px;
        border: none;
        align-items: center;
    }
    input:focus {
        outline: none;
    }

    p {
        color: white;

        font-size: 40px;
        margin-top: 0px;
    }

    h1, h2 {
        color: white;
    }
    
    h2 {
        margin-top: 150px;
    }
  

</style>