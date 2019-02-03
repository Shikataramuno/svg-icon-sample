<template>
  <g>
  <rect
     ry="1"
     rx="1"
     y="0.75"
     x="0.75"
     height="16.5"
     width="16.5"
     id="rect4136"
     style="opacity:1;fill:none;fill-opacity:1;stroke-width:1.5;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1" />
  <circle
     r="6"
     cy="9"
     cx="9"
     id="path4139"
     style="opacity:1;fill:none;fill-opacity:1;stroke-width:1.5;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1" />
  <circle
     r="3"
     cy="9"
     cx="9"
     id="path4141"
     style="opacity:1;fill-opacity:1;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1" />
  <rect v-on:click="clicked"
     ry="1"
     rx="1"
     y="0"
     x="0"
     height="18"
     width="18"
     id="rect4145"
     style="opacity:1;fill-opacity:0;stroke:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1" />
  </g>
</template>

<script lang="ts">
import { Component, Emit, Vue } from 'vue-property-decorator';

@Component
export default class IconMic extends Vue {
  // name: string = 'IconMic';
  @Emit('clicked')
  clicked(): void {
    console.log('icon-mic clicked');
  }
}
</script>
