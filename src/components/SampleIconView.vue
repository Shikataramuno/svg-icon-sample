<template>
  <div class="container-filed">
    <h1>Vue + Typescript で 自前のアイコンを操作してみる</h1>
    <div class="sample-icon-field">
      <icon-base icon-color="#ff0000" width=30 height=30 icon-name="sample"><icon-sample @clicked="iconClicked"/></icon-base>
      <p>{{message}}</p>
    </div>
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
  message: string = '';
  clickCount: number = 0;
  iconClicked(): void {
    alert('アイコンがクリックされました！');
    this.clickCount++;
    this.message = 'アイコンが ' +  this.clickCount + '回 クリックされました！';
  }
  initialize(): void {
    this.clickCount = 0;
    this.message = '初期化されました';
  }
  created(): void {
    console.log('SampleIconView.created');
    this.initialize();
  }
}
</script>

<style scoped>
.sample-icon-field {
  padding: 5px;
  width: 100%;
}
</style>
