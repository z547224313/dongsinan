<template>
  <div class="index-item" @click="clickItem">
      <div class="icon">
        <span :class="className"></span>
      </div>
      <div class="name">
        <span>{{ citem.name }}</span>
      </div>
  </div>
</template>

<script lang="ts">
import {Component, Prop, Vue} from 'vue-property-decorator';
import {IndexClipType} from "@/type";

@Component
export default class IndexItem extends Vue {
  @Prop()
  private citem:IndexClipType

  get className() {
    return `iconfont ${this.citem.icon}`
  }

  private clickItem() {
    window.location.href = this.citem.href
  }
}
</script>

<style scoped lang="less">
.index-item {
  width: 31.5%;
  margin-bottom: 15px;
  box-sizing: border-box;
  height: 100px;
  border: 1px red solid;
  border-radius: 5px;
  padding: 10px;
  .icon {
    color: red;
    margin-bottom: 5px;
    span {
      font-size: 50px;
    }
  }
}
</style>
