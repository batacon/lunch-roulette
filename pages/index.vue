<template>
  <div class="roulette">
    <h1>昼飯ルーレット</h1>
    <button @click="spinRoulette">今日の昼飯は？</button>
    <h2 v-if="showLunch">{{ selectedLunch }}だ！</h2>
    <h1 v-if="spinCount > 4">何回やんねん！</h1>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {
      lunchSelects: [
        'ラーメン',
        'カレー',
        '牛丼',
        'うどん',
        'ハンバーガー',
        '餃子',
        'パスタ',
        '焼肉',
        '唐揚げ',
        'ハンバーグ',
        '魚',
      ],
      showLunch: false,
      selectedLunch: '',
      randomIndex: 0,
      spinCount: 0,
    }
  },
  methods: {
    spinRoulette() {
      this.randomIndex = Math.floor(Math.random() * this.lunchSelects.length)
      this.selectedLunch = this.lunchSelects[this.randomIndex]
      this.showLunch = true
      this.spinCount++
    },
  },
})
</script>

<style>
.roulette {
  width: 400px;
  margin: 0 auto;
}
</style>
