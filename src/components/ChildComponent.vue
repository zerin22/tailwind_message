<template>
    <div class="child-component">
      <h2 class="font-serif text-2xl text-center font-bold text-red-400">Welcome to the Child Component</h2>
      <button class="hover:text-teal-200 text-slate-100 bg-cyan-900 font-mono" @click="emitCustomMessage">Emit Custom Message</button>
    </div>
  </template>
  
  <script>
  import { defineEmits } from 'vue';
  
  export default {
    emits: ['messageEmitted'],
    setup(props, { emit }) {
      const emitCustomMessage = () => {
        const customMessage = 'Hello this message from Child Component!';
        emit('messageEmitted', customMessage);
      };
  
      return {
        emitCustomMessage,
      };
    },
  };
  </script>

<style scoped>
    .child-component {
  background-color: #ffffff;
  padding: 20px;
  margin-top: 20px;
}

.child-component h2 {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

.child-component p {
  margin-bottom: 10px;
}

.child-component button {
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
  