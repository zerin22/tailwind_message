<template>
    <div class="bg-gray-500 p-6">
        <h2 class="font-serif text-2xl text-center font-bold text-cyan-400">Welcome to the Parent Component</h2>
        <ChildComponent :message="message" @messageEmitted="handleMessage" />
        <p class="font-serif text-lg  mt-2 mb-2 text-green-300 ">Child Component  {{ receivedMessage }}</p>
    </div>
</template>

<script>
import { defineProps, ref } from 'vue';
import ChildComponent from './ChildComponent.vue';

export default {
    components: {
        ChildComponent,
    },
    setup() {
        const receivedMessage = ref('');

        const handleMessage = (message) => {
            receivedMessage.value = message;
        };

        return {            
            receivedMessage,
            handleMessage,
        };
    },
};
</script>


