<script setup lang="ts">/**
 * @desc Описание компонента
 * Ссылка на макет - https://www.figma.com/design/hash
 */
import {onMounted, ref} from "vue";
import Card from "./Card.vue";
import {cards, ICard} from "../assets/data/cards.ts";
import Button from "./Button.vue";
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
// #endregion  

// #region Data
let isGameStart = ref<boolean>(false);
let shuffleCards = ref<ICard[]>([]);
// #endregion  

// #region Methods
function startGame() {
  shuffleCards.value = cards.concat(cards);

  for (let i = shuffleCards.value.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [shuffleCards.value[i], shuffleCards.value[j]] = [shuffleCards.value[j], shuffleCards.value[i]];
  }

  isGameStart.value = true;

  setTimeout(() => {
    isGameStart.value = false;
  }, 1500);
}
// #endregion  

// #region Computed  
// #endregion  

// #region Lifecycle
onMounted(() => {
  startGame();
})
// #endregion 

// #region Watchers
// #endregion
</script>

<template>
  <div>
    <Button @start-game="startGame" />

    <div :class="$style.GameBoard">
      <Card v-for="card in shuffleCards" :isGameStart="isGameStart">
        {{ card.icon }}
      </Card>
    </div>
  </div>
</template>

<style module>
.GameBoard {
    padding: 2rem;
    margin: 0 auto;
    width: fit-content;
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-template-rows: repeat(6, 1fr);
    grid-column-gap: 1rem;
    grid-row-gap: 1rem;
}
</style>
