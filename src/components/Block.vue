<template>
    <div class="block" v-if="showBlock" @click="stopTimer">Click Me {{delay}} </div>
</template>

<script>
export default {
    props : ["delay"],
    data(){
        return{
            showBlock : false,
            score : 0,
            timer : null,
        }
    },
    mounted(){
        // console.log(" Mounted");
        setTimeout(()=>{
            this.showBlock = true;
            this.startTimer()
        },this.delay)
    },
    methods : {
        startTimer(){
            this.timer = setInterval(()=>{
                this.score += 50
            },50)
        },
        stopTimer(){
            clearInterval(this.timer);
            this.$emit("endGame",this.score)
        }
    }
    // updated(){
    //     console.log("Data Updated");
    // },
    // beforeCreate(){
    //     console.log("Before Created");
    // },
    // created(){
    //     console.log("Created");
    // },
    // beforeMount(){
    //     console.log("befor mounted");
    // },
    // beforeUpdate(){
    //     console.log("before updated");
    // }
}
</script>

<style>
    .block{
        background-color: aqua;
        width: 400px;
        height: 300px;
        margin: 20px auto;
        padding-top: 30px;
        border-radius: 30px;
    }
</style>