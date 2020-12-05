<template>
  <div>
    <pinch-zoom
      :minScale="1"
      :limitZoom="10"
      :zoomControlScale="10"
      :doubleTapScale="10"
      @mouseup="onMouseUp"
      @touchend="onTouchEnd"
      @wheel="onWheel"
    >
      <img
        src="https://images.unsplash.com/photo-1544606402-e522c304b027?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1564&q=80"
      />
    </pinch-zoom>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import { IvyPinch } from './ivypinch'; 

import PinchZoom from './components/PinchZoom.vue'; 

@Component({
    components: {
        'pinch-zoom': PinchZoom
    },
})
export default class myLib extends Vue {
  public onMouseUp(details: any): void {
    console.log("mouseup %s", JSON.stringify(details))
  }
  public onTouchEnd(detail: any): void {
    console.log("touchend %s", JSON.stringify(detail))
  }
  public onWheel(detail: any): void {
    console.log("wheel %s", JSON.stringify(detail))
  }
}
</script>