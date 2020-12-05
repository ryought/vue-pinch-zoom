<template>
  <div>
    <pinch-zoom
      :minScale="1"
      :limitZoom="10"
      :zoomControlScale="10"
      :doubleTapScale="10"
      @mouseup="mouseup"
      @didScale="didScale"
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
  public didScale(details: any): void {
    console.log("didScale %s", JSON.stringify(details))
  }
  public mouseup(details: any): void {
    console.log("mouseup %s", JSON.stringify(details))
  }
}
</script>