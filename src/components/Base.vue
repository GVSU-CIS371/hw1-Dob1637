<template>
  <div class="baseBeverage"></div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { BaseBeverageType } from '../stores/beverage';

type Props = {
  base_Color: BaseBeverageType;
};
const props = defineProps<Props>();
const coLor = ref(props.base_Color.color)
</script>


<style scoped>
.baseBeverage {
  background-color: v-bind(coLor);
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
</style>
