<template>
  <div class="index">
    <IndexItem v-for="item in IndexClipsArray" :key="item.name" :citem="item"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import { IndexClips } from "@/common/common";
import IndexItem from "@/components/base/IndexItem.vue";
import {IndexClipType} from "@/type";

@Component({
  components: {IndexItem}
})
export default class Index extends Vue {
  private IndexClipsArray: IndexClipType[] = IndexClips

}
</script>

<style scoped lang="less">
.index {
  display: flex;
  flex-wrap: wrap;
  padding-top: 15px;
  width: 100%;
  justify-content: space-between;
}
</style>
