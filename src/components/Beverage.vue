<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Creamer />
      </template>
      <template v-slot:mid>
        <Syrup />
      </template>
      <template v-slot:bottom>
        <Base v-bind:base_Color="baseCol"/>
      </template>
    </Contents>
  </Mug>
</template>
<script setup lang="ts">
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";
import { BaseBeverageType } from "../stores/beverage";

type Props = {
  isIced: boolean;
  baseCol: BaseBeverageType;
  syrCol: string;
  creCol: string;
};
defineProps<Props>();
</script>
