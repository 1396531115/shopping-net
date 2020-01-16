<template>
  <div class="m-menu">
    <dl class="nav" @mouseleave="mouseleave">
      <dt>全部分类</dt>
      <dd v-for="(item, index) in menu" :key="index" @mouseenter="mouseenter">
        <i :class="item.type">
          {{ item.name }}
          <span class="arrow"></span>
        </i>
      </dd>
    </dl>
    <div class="detail" v-if="type" @mouseenter="enterDetail" @mouseleave="leaveDetail">
      <template v-for="(item, index) in curDetail">
        <h4 :key="index">{{item.title}}</h4>
        <span v-for="v in item.child" :key="v">{{v}}</span>
      </template>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      type: '',
      _time: '',
      menu: [
        { type: "food", name: "美食", child: [{title: '美食', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] },
        { type: "waimai", name: "外卖", child: [{title: '外卖', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] },
        { type: "hotel", name: "酒店", child: [{title: '酒店', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] },
        { type: "ming", name: "榛果民宿", child: [{title: '榛果民宿', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] },
        { type: "movie", name: "猫眼电影", child: [{title: '猫眼电影', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] },
        { type: "ticket", name: "机票 / 火车票", child: [{title: '机票 / 火车票', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] },
        { type: "play", name: "休闲娱乐 / KTV", child: [{title: '休闲娱乐 / KTV', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] },
        { type: "life", name: "生活服务", child: [{title: '生活服务', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] },
        { type: "butiful", name: "丽人 / 美发", child: [{title: '丽人 / 美发', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] },
        { type: "marry", name: "结婚 / 婚纱摄影", child: [{title: '结婚 / 婚纱摄影', child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']}] }
      ]
    };
  },
  computed: {
    curDetail() {
      let data = this.menu.filter(item => item.type === this.type);
      if (data) {
        return data[0].child
      }
    }
  },
  methods:   {
    mouseleave() {
      this._time = setTimeout(() => {
        this.type = ''
      }, 150)
    },
    mouseenter(e) {
      if(e.target) this.type = e.target.querySelector('i').className;
      console.log(this.type)
    },
    leaveDetail() {
      this.type = ''
    },
    enterDetail() {
      clearTimeout(this._time)
    }
  }
};
</script>

<style></style>
