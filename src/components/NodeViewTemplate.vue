<template>
  <g v-if="tag" class=" ">
    <rect fill="#C0C0C0" width="285" height="100" transform="translate(2 2)"></rect>
    <rect fill="#FFFFFF" stroke="#C0C0C0" width="285" height="100"></rect>
    <rect width="285" height="2" :fill="statusColor"></rect>
    <use :xlink:href="'#' + tag.icon" :transform="zoom >= 1 ? 'scale(0.85) translate(15 10)' : 'scale(0.75) translate(15 30)'"></use>
    <use v-show="zoom >= 1" :xlink:href="'#' + tag.status + '_icon'" transform="translate(26 84)"></use>
    <g :fill="focused ? '#FFBB33' : 'transparent'" class="hover-indicator">
      <rect width="3" height="100"></rect>
      <rect width="3" height="100" transform="translate(282 0)"></rect>
      <rect width="285" height="3"></rect>
      <rect width="285" height="3" transform="translate(0 97)"></rect>
    </g>
    <g :style="{ fontSize: zoom >= 1 ? '10px' : '15px', fontFamily: 'Roboto,sans-serif', fontWeight: 300, fill: '#444' }">
      <text :transform="zoom >= 1 ? 'translate(100 25)' : 'translate(75 40)'" :style="{ fontSize: zoom >= 1 ? '16px' : '26px', fill: '#336699' }">{{tag.id}}</text>
      <text :transform="zoom >= 1 ? 'translate(100 45)' : 'translate(75 70)'" style="text-transform: uppercase; font-weight: 400">{{positionFirstLine}}</text>
      <text :transform="zoom >= 1 ? 'translate(100 57)' : 'translate(75 90)'" style="text-transform: uppercase; font-weight: 400">{{positionSecondLine}}</text>
      <text v-show="zoom >= 1" transform="translate(100 72)">{{tag.email}}</text>
      <text v-show="zoom >= 1" transform="translate(100 88)">{{tag.phone}}</text>
      <text v-show="zoom >= 1" transform="translate(170 88)">{{tag.fax}}</text>
    </g>
  </g>
</template>

<script>
export default {
  name: 'NodeViewTemplate'
}
</script>

<style scoped>

</style>
