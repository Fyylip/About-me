<template>
  <div class="slider-container" @touchstart="onTouchStart" @touchmove="onTouchMove">
    <div class="slides-wrapper">
      <div class="slide-container">
        <div class="slides" :style="{ transform: `translateX(-${(active - 1) * 50}%)` }">
          <div class="slide" v-for="index in slides.length" :key="index" :style="{ backgroundColor: slides[index - 1].color }">
            Slide {{ index }}
          </div>
        </div>
      </div>
    </div>
    <span class="prev left-arrow" @click="move(-2)"><img src="../assets/415288003_917405659587132_8109731057855356949_n.png" alt=""></span>
    <span class="next right-arrow" @click="move(2)"><img src="../assets/415288003_917405659587132_8109731057855356949_n2.png" alt=""></span>
  </div>
</template>
  
  <script>
  export default {
    name: 'Slider-component',
    data() {
      return {
        slides: [
          { index: 1, color: 'red' },
          { index: 2, color: 'green' },
          { index: 3, color: 'blue' },
          { index: 4, color: 'yellow' },
          { index: 5, color: 'green' },
          { index: 6, color: 'pink' },
        ],
        active: 1,
        touchStartX: 0,
      };
    },
    methods: {
      move(amount) {
        let newIndex = this.active + amount;
        if (newIndex > this.slides.length + 1) {
          newIndex = 1;
        } else if (newIndex <= 0) {
          newIndex = this.slides.length + 1;
        }
        this.active = newIndex;
      },
      onTouchStart(event) {
        this.touchStartX = event.touches[0].clientX;
      },
      onTouchMove(event) {
        const touchEndX = event.touches[0].clientX;
        const touchDeltaX = touchEndX - this.touchStartX;
        const threshold = 0;
  
        if (touchDeltaX > threshold) {
          this.move(-1);
        } else if (touchDeltaX < -threshold) {
          this.move(1);
        }
      },
    },
  };
  </script>
  
  <style src="../assets/global.css"></style>