<template>
  <svg xmlns="http://www.w3.org/2000/svg" 
    :width="width" 
    :height="height" 
    viewBox="0 0 18 18" 
    :aria-labelledby="iconName" 
    role="presentation"
  >
    <title :id="iconName" lang="en">{{iconName}} icon</title>
    <g :fill="iconColor" :stroke="iconColor">
      <slot />
    </g>
  </svg>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class IconBase extends Vue {
  // name: string = 'IconBase';
  @Prop({default: 'box'}) iconName!: string;
  @Prop({default: 18}) width!: number | string;
  @Prop({default: 18}) height!: number | string;
  @Prop({default: 'currentColor'}) iconColor!: string;
}
</script>

<style scoped>
svg {
  display: inline-block;
  vertical-align: baseline;
  margin-bottom: -2px; /* yes, I'm that particular about formatting */
}
</style>