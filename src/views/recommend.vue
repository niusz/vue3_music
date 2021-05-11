<template>
  <div class="recommend">
    <div class="slider-wrapper">
      <div class="slid</slider>er-content">
        <slider v-if="sliders.length" :sliders="sliders"></slider>
      </div>
    </div>
  </div>
</template>

<script>
import { getRecommend } from '@/service/recommend'
import Slider from '@/components/base/slider/slider'
export default {
  name: 'recommend',
  components: {
    Slider
  },
  data() {
    return {
      sliders: []
    }
  },
  async created() {
    const result = await getRecommend()
    this.sliders = result.sliders
  }
}
</script>

<style>

</style>
