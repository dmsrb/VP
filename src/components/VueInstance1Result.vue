<template>
  <div class="hello">
    <h1>{{ standardNum }} + {{ changedNum }} : {{ sumNum }}</h1>
    <h1>{{ standardNum }} - {{ changedNum }} : {{ minorNum }}</h1>
    <h1>{{ standardNum }} * {{ changedNum }} : {{ multiplyNum }}</h1>
    <h1>{{ standardNum }} / {{ changedNum }} : {{ divisionNum }}</h1>
    <b-button
      class="m-1"
      @click="upNum"
    >
      숫자 올리기
    </b-button>
    <b-button
      class="m-1"
      @click="downNum"
    >
      숫자 내리기
    </b-button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Component from 'vue-class-component';
import { Watch } from 'vue-property-decorator';

@Component({})
export default class VueIstanceResult extends Vue {
  private standardNum = 1;

  private changedNum = 1;

  get sumNum(): number {
    return this.standardNum + this.changedNum;
  }

  get minorNum(): number {
    return this.standardNum - this.changedNum;
  }

  get multiplyNum(): number {
    return this.standardNum * this.changedNum;
  }

  get divisionNum(): string {
    return (this.standardNum / this.changedNum).toFixed(2);
  }

@Watch('changedNum')
  onChangedNum(value: number, oldValue : number) :void {
    console.log('value : ', value);
    console.log('oldValue : ', oldValue);
  }

upNum():void {
  this.changedNum += 1;
}

downNum():void{
  this.changedNum -= 1;
}
}
</script>
