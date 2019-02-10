<template>
  <div class="sample-icon-field">
    <icon-base icon-color="#ff0000" width=30 height=30 icon-name="sample"><icon-sample @clicked="iconClicked"/></icon-base>
    <div class="message">{{message}}</div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import IconBase from './IconBase.vue';
import IconSample from './icons/IconSample.vue';

@Component({
  components: {
    IconBase,
    IconSample,
  },
})
export default class SampleIconView extends Vue {
  name: string = 'SampleIconView';
  message: string = ' ↑ クリック^2 ！';
  clickCount: number = 0;
  iconClicked(): void {
    alert('アイコンがクリックされました！');
    this.clickCount++;
    this.message = 'アイコンが ' +  this.clickCount + '回 クリックされました！';
  }
  created(): void {
    console.log('SampleIconView.created');
  }
}
</script>

<style scoped>
.sample-icon-field {
  padding: 5px;
  width: 100%;
}
.message {
  line-height: 30px;
}
</style>
