<template>
  <!-- 资讯列表组件 -->
  <view class="news-list">
    <view v-for="(news, index) in newsList" :key="index" @click="viewNews(news.id)" class="news-item">
      <view class="news-message">{{news.message}}</view>
      <view class="news-time">{{news.time}}</view>
      <img :src="news.pic" alt="">
    </view>
  </view>
</template>

<script>
export default {
  props: ['newsList', 'url'],
  methods: {
    // 查看资讯详情
    viewNews (id) {
      mpvue.navigateTo({ url: this.url })
    }
  }
}
</script>

<style lang="scss" scoped>
.news-list .news-item {
  border: 1px solid #BBBBBB;
  padding: 10px 104px 10px 15px;
  position: relative;
  margin-bottom: 5px;

  .news-message {
    font-size: 12px;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
  }

  .news-time {
    font-size: 11px;
    color: #A29B9B;
  }

  img {
    width: 84px;
    height: 54px;
    position: absolute;
    top: 10px;
    right: 10px;
  }
}
</style>
