<template>
  <div class="search-panel">
    <el-row class="m-header-searchbar">
      <el-col
        :span="3"
        class="left"
      >
        <img
          src="//s0.meituan.net/bs/fe-web-meituan/e5eeaef/img/logo.png"
          alt="美团"
        >
      </el-col>
      <el-col
        :span="15"
        class="center"
      >
        <div class="wrapper">
          <el-input
            v-model="search"
            placeholder="搜索商家或地点"
            @focus="focus"
            @blur="blur"
            @input="input"
          />
          <button class="el-button el-button--primary">
            <i class="el-icon-search" />
          </button>
          <!-- 热门搜索  -->
          <dl v-show="isShowHotPlace" class="hotPlace">
            <dt>热门搜素</dt>
            <dd v-for="(item,i) in hotPlace" :key="i">
              {{ item }}
            </dd>
          </dl>
          <!-- 搜索列表 -->
          <dl v-show="isShowSearchList" class="searchList">
            <dd v-for="(item,i) in searchList" :key="i">
              {{ item }}
            </dd>
          </dl>
        </div>
        <!-- 建议 -->
        <p class="suggest">
          <a>故宫博物院</a>
          <a>故宫博物院</a>
          <a>故宫博物院</a>
          <a>故宫博物院</a>
        </p>
        <ul class="nav">
          <li>
            <nuxt-link
              to="/"
              class="takeout"
            >
              美团外卖
            </nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/"
              class="movie"
            >
              猫眼电影
            </nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/"
              class="hotel"
            >
              美团酒店
            </nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/"
              class="apartment"
            >
              民宿/公寓
            </nuxt-link>
          </li>
          <li>
            <nuxt-link
              to="/"
              class="business"
            >
              商家入驻
            </nuxt-link>
          </li>
        </ul>
      </el-col>
      <el-col
        :span="6"
        class="right"
      >
        <ul class="security">
          <li>
            <i class="refund" />
            <p class="txt">
              随时退
            </p>
          </li>
          <li>
            <i class="single" />
            <p class="txt">
              不满意免单
            </p>
          </li>
          <li>
            <i class="overdue" />
            <p class="txt">
              过期退
            </p>
          </li>
        </ul>
      </el-col>
    </el-row>
  </div>
</template>

<script>
// import _ from 'lodash'
export default {
  data () {
    return {
      search: '', // 搜索内容
      isFocus: false, // 是否是聚焦状态
      hotPlace: ['故宫', '故宫', '故宫', '故宫'],
      searchList: ['故宫博物馆', '故宫博物馆', '故宫博物馆', '故宫博物馆']
    }
  },
  computed: {
    isShowHotPlace () {
      return this.isFocus && !this.search
    },
    isShowSearchList () {
      return this.isFocus && this.search
    }
  },
  methods: {
    focus () {
      this.isFocus = true
    },
    blur () {
      // 延后失去焦点使得能够正常点击链接跳转
      setTimeout(() => {
        this.isFocus = false
      }, 100)
    },
    input () {
      window.console.log('input')
    }
  }
}
</script>

<style lang="scss">
</style>
