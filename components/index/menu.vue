<template>
  <div class="m-menu">
    <dl class="nav">
      <dt>全部分类</dt>
      <dd v-for="(item, index) in menu" :key="index">
        <i :class="item.type">{{ item.name }}<span class="arrow"></span></i>
      </dd>
    </dl>
  </div>
</template>
<script>
export default {
  data() {
    return {
      menu: [
        {type: 'food', name: '美食'},
        {type: 'food', name: '外卖'},
        {type: 'food', name: '酒店'},
        {type: 'food', name: '榛果民宿'},
        {type: 'food', name: '猫眼电影'},
        {type: 'food', name: '机票 / 火车票'},
        {type: 'food', name: '休闲娱乐 / KTV'},
        {type: 'food', name: '生活服务'},
        {type: 'food', name: '丽人 / 美发'},
        {type: 'food', name: '结婚 / 婚纱摄影'},
      ]
    }
  }
}
</script>

<style></style>
