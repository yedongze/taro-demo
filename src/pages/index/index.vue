<template>
  <scroll-view
    class="base-scroll-view"
    :scroll-y="true"
    style="height: 400px;width: 100%;background-color: antiquewhite;"
    :refresher-enabled="true"
    :refresher-threshold="100"
    :refresher-triggered="state.triggered"
    @refresherrefresh="onRefresh"

  >
  </scroll-view>
</template>

<script lang="ts" setup>
import { reactive } from "vue";
const state = reactive({
  triggered: false
});

const onRefresh = ()=>{
  state.triggered = true
  console.log('start',state.triggered)
  setTimeout(() => {
    state.triggered = false
     console.log('end',state.triggered)
  }, 2000);
}
</script>
