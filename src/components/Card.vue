<script setup lang="ts">/**
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
interface IProps {
  isGameStart: boolean
}
// #region Props
defineProps<IProps>()
// #endregion  

// #region Emits  
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
  <div :class="$style.Card">
      <span :class="[$style.image, isGameStart ? $style.show : '']"><slot/></span>
  </div>
</template>

<style module>
.Card {
  border: 1px solid gray;
  width: 4rem;
  height: 4rem;
  display: flex;
  border-radius: 1rem;
  justify-content: center;
  align-items: center;
  transition: all 0.3s ease-in-out;
}

.Card:hover {
  cursor: pointer;
  scale: 1.2;
}

.image {
  display: none;
}

.show {
  cursor: not-allowed;
  display: block;
}
</style>
