<template>
  <div
    class="item"
    :style="{
      'grid-row': `${item.row}`,
      'grid-column': `${item.column}`,
      'background-image': `url(${item.image})`
    }"
  >
    <span
      v-for="text in item.text"
      :key="text.string"
      :style="{
        'color': `${text.color}`,
        'font-size': `${text.fontSize}`,
        'display': 'flex',
        'align-self':`${text.align}`,
        'justify-self': `${text.justify}`,
      }"
    >
      {{ text.string }}
    </span>
    </span>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      default () {
        return {
          row: null,
          column: null,
          image: '',
          text: [
            {
              string: '',
              justify: 'center',
              align: 'center',
              color: 'black',
              fontSize: '14px'
            }
          ]
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.item {
  display: flex;
  padding: 10px;
  background-size: cover;
}
</style>
