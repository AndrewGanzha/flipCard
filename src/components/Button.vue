<script setup lang="ts">
/**
 * @desc Описание компонента
 * Ссылка на макет - https://www.figma.com/design/hash
 */

// #region Imports  
// Types  
// Utils  
// Vue  
// Pinia  
// Components  
// #endregion  

// #region Interfaces  
// #endregion  

// #region Props  
// #endregion  

// #region Emits
defineEmits(['startGame'])
// #endregion  

// #region Data  
// #endregion  

// #region Methods  
// #endregion  

// #region Computed  
// #endregion  

// #region Lifecycle  
// #endregion 

// #region Watchers
// #endregion
</script>

<template>
  <div :class="$style.container">
    <button :class="$style.button" @click="$emit('startGame')">
      Начать новую игру
    </button>
  </div>
</template>

<style module>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.button {
  cursor: pointer;
  background: none;
  font-size: 2rem;
  border-radius: 1rem;
  padding: 1rem;
}
</style>
