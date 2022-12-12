<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <StopWatch :seconds="seconds"/>   
        <button class="button" @click="startCount" :disabled="active">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span>play</span>
        </button>
        <button class="button" @click="stopCount" :disabled="!active">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
        </button>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import StopWatch from './stopwatch.vue';

export default defineComponent({
    name:'TimerWatch',
    emits:['whenFinish'],
    components:{
        StopWatch,
    },
    data(){
        return {
            seconds: 0,  
            cronometro: 0,
            active: false,
        }
    },
    methods:{
        startCount(){
            this.active = true
            this.cronometro = setInterval(()=>{
                console.log('incrementando', this.seconds);
                this.seconds++;
            }, 1000)
        },
        stopCount(){
            this.active = false
            clearInterval(this.cronometro)
            this.$emit('whenFinish', this.seconds);
            this.seconds = 0;
        },
    }
})
</script>

<style scoped>
</style>