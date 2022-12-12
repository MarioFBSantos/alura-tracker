<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Form to create new task">
                <input type="text" v-model="description" class="input" placeholder="Qual tarefa você deseja iniciar?" />
            </div>
            <div class="column">
                <TimerWatch @whenFinish="finishTask"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TimerWatch from './timer.vue';
export default defineComponent({
    name:'FormTask',
    data(){
        return{
            description: ''
        }
    },
    components:{
        TimerWatch
    },
    methods:{
        finishTask( duration: number ): void{
            console.log(this.description, duration);
            this.description = '';
        }
    }
})
</script>