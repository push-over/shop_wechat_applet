<template>
  <div>
    <van-search :value="value"
                placeholder="请输入搜索关键词"
                use-action-slot
                @search="onSearch">
      <view slot="action"
            @tap="onSearch">搜索</view>
    </van-search>
    <van-tabs :active="active"
              @change="onChange">
      <van-tab title="推荐"></van-tab>
      <van-tab title="手机"></van-tab>
      <van-tab title="智能"></van-tab>
      <van-tab title="电视"></van-tab>
      <van-tab title="笔记本"></van-tab>
      <van-tab title="家电"></van-tab>
    </van-tabs>
    <swiper class="swiper"
            :indicator-dots="true"
            :autoplay="true"
            :interval="5000"
            :duration="1000">
      <block v-for="(item, index) in imgUrls"
             :index="index"
             :key="index">
        <swiper-item>
          <image :src="item"
                 class="slide-image"
                 mode="aspectFill" />
        </swiper-item>
      </block>
    </swiper>
    <div class="contain">
      <div class="item"><img src="https://img.yzcdn.cn/vant/logo.png"><span>新品发布</span></div>
      <div class="item"><img src="https://img.yzcdn.cn/vant/logo.png"><span>小米闪购</span></div>
      <div class="item"><img src="https://img.yzcdn.cn/vant/logo.png"><span>1分拼团</span></div>
      <div class="item"><img src="https://img.yzcdn.cn/vant/logo.png"><span>米粉卡</span></div>
      <div class="item"><img src="https://img.yzcdn.cn/vant/logo.png"><span>每日甄选</span></div>
      <div class="item"><img src="https://img.yzcdn.cn/vant/logo.png"><span>以旧换新</span></div>
      <div class="item"><img src="https://img.yzcdn.cn/vant/logo.png"><span>活动频道</span></div>
      <div class="item"><img src="https://img.yzcdn.cn/vant/logo.png"><span>礼品卡</span></div>
    </div>
    <van-notice-bar scrollable="false"
                    text="足协杯战线连续第2年上演广州德比战，上赛季半决赛上恒大以两回合5-3的总比分淘汰富力。" />
    <div class="recommend">
      <div class="recommend-one">
        <image src="https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640"
               class="slide-image"
               mode="aspectFill" />
      </div>
      <div class="recommend-two">
        <image src="https://images.unsplash.com/photo-1551214012-84f95e060dee?w=640"
               class="slide-image"
               mode="aspectFill" />
      </div>
      <div class="recommend-three">
        <image src="https://images.unsplash.com/photo-1551446591-142875a901a1?w=640"
               class="slide-image"
               mode="aspectFill" />
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      value: '',
      active: 0,
      imgUrls: [
        'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
        'https://images.unsplash.com/photo-1551214012-84f95e060dee?w=640',
        'https://images.unsplash.com/photo-1551446591-142875a901a1?w=640'
      ]
    }
  },

  methods: {
    onSearch (event) {
      console.log(event)
    },
    onChange (event) {
      console.log(event)
    }
  }
}
</script>

<style scoped>
.slide-image {
  width: 100%;
}
.contain {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  align-content: space-around;
  height: 160px;
}

.item {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  width: 56px;
  height: 70px;
  font-size: 14px;
  color: #a6a6a6;
}

.item image {
  width: 36px;
  height: 36px;
}

.recommend {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  width: 100%;
  height: 267px;
}
.recommend-one,
.recommend-one image {
  width: 189px;
  height: 267px;
}

.recommend-two,
.recommend-two image {
  width: 186px;
  height: 129px;
}

.recommend-three,
.recommend-three image {
  margin-top: 3px;
  width: 186px;
  height: 132px;
}
</style>

