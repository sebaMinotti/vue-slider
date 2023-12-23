<template>
    <div class="myslider">
        <section  class="left harrow">
                <div class="containerHarrow">
                    <i @click="prev" class="fa-solid fa-circle-arrow-left"></i>
                </div>
        </section>


        <section class="center" >
            <img :src="fotografie[counter]" alt="">
             <div class="boxPallini">
                <i @click="clickpallino(index)" v-for="(foto,index) in fotografie" :key="foto" :class="(counter===index)?'active':'inactive'" class="fa-solid fa-circle"></i>
             </div>
        </section>
        

        <section class="right harrow">
            <div class="containerHarrow">
              
                <i @click="next" class="fa-solid fa-circle-arrow-right"></i>
            </div>
        </section>
    </div>
</template>

<script>
    export default {
        name:'MySlider',
        data() {
            return {
                     counter:0,
                      fotografie:['https://disneylandparis-news.com/app/uploads/2022/05/KV-Marvel-Avengers-Campus-scaled-1.jpg','https://d23.com/app/uploads/2019/04/1180w-600h_042419_avengers-endgame-need-to-know-780x440.jpg','https://miro.medium.com/v2/resize:fit:1400/1*QF3j_DQQsxmH7uK5o5CdqA.jpeg','https://media-assets.wired.it/photos/615f10bf0f2b3dd590a02651/master/w_1600%2Cc_limit/1472206765_Chris-Evans-Captain-America-Trilogy.jpg'],
                      
            }
        },
        mounted() {
            
        },
        methods: {
            next:function() {
               
                this.counter++
                if(this.counter > this.fotografie.length-1){
                    this.counter=0
                }
            },
            prev:function(){
              
                this.counter--
                if(this.counter < 0){
                    this.counter = this.fotografie.length-1
                }
            },
            clickpallino:function(index){
                
                  this.counter=index
            }
        },
    }
</script>

<style scoped>
.myslider{
    width: 80%;
    height: 40rem;
    margin: 10px auto;display: flex;flex-direction: row;
    cursor: pointer;
}
.harrow{
    width: 10%;height: 100%;
    display: flex;
    align-items: center;
}
.center{
    
    width: 80%;
    height: 100%;
    position: relative;
    transition: opacity 0.5s ease-in-out;
}
.center > img{
    width: 100%;height: 100%;
    border-radius: 3%;
}
.boxPallini{

    width: 400px;
    height: 4rem;
    position: absolute;
    bottom: 10px;
    left: 50%;margin-left: -200px;
    display: flex;justify-content: center;flex-direction: row;padding: 5px;align-items: center;
}
.boxPallini i{
    margin: 5px;font-size:1.5rem;
}
.containerHarrow{
    width: 100%;height: 4rem;
    display: flex;align-items: center;justify-content: center;
}
.containerHarrow i{
    font-size: 2.5rem;
}
.active{
    color: darkorange;
}
.inactive{
    color: white;
}

</style>