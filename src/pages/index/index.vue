<template>
  <view style="height: 300px;">
    <picker-view :value="value" @change="onChange">
      <picker-view-column v-for="(column, index) in columns">
        <view v-for="(item, index) in column.list" :key="index">{{ item.name }}</view>
      </picker-view-column>
    </picker-view>
  </view>
</template>

<script>
  export default {
    name: "Index",
    data() {
      return {
        columns: [
          {
            list: [
              { name: '选项一' },
              { name: '选项二' },
              { name: '选项三' },
            ],
          }
        ],
        value: [1],
      }
    },
    methods: {
      onChange: function(e) {
        console.log('onChange', e.detail.value)
        this.value = e.detail.value
      }
    }
  }
</script>