<template>
  <div>
    <h1>Quotes added</h1>
    <div class="progress-wrap">
      <div
        class="progress-state"
        v-if="quotesQuantity === maxquotes"
        :style="{'width': '100%', 'background-color': 'red'}"
      >{{ quotesQuantity }} / {{ maxquotes }}</div>
      <div
        class="progress-state"
        v-else
        :style="{'width': ((quotesQuantity * 100) / maxquotes) + '%'}"
      >{{ quotesQuantity }} / {{ maxquotes }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["quotesQuantity", "maxquotes"]
};
</script>

<style scoped>
.progress-wrap {
  min-width: 100%;
  height: 40px;
  background-color: cornsilk;
  border-radius: 6px;
  overflow: hidden;
  cursor: grab;
}
.progress-state {
  background-color: darkblue;
  height: inherit;
  color: white;
  font-size: 16px;
  line-height: 20px;
  text-align: center;
  padding-top: 9px;
}
</style>> 
