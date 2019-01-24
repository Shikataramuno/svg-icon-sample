<template>
  <div class="container-filed">
    <h1>Vue + Typescript で 自前のアイコンを操作してみる</h1>
    <div class="sample-icon-field">
      <img src="../assets/SampleIcon.png" class="icon" width='30px' height='30px' @click="iconClicked"/>
      <button @click="iconClicked">ダイアログの表示</button>
      <p>{{message}}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
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
