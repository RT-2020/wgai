<template>
  <div class="logo" style="background-color: #fff !important">
    <router-link :to="routerLinkTo" class="logo-link">
      <img src="/logo.png" alt="煤矿AI模型管理系统" class="logo-img" />
      <h1 v-if="showTitle" class="logo-text">{{ title }}</h1>
    </router-link>
  </div>
</template>

<script>
import { mixin } from '@/utils/mixin.js'

export default {
  name: 'Logo',
  mixins: [mixin],
  props: {
    title: {
      type: String,
      default: '煤矿AI模型管理系统',
      required: false,
    },
    showTitle: {
      type: Boolean,
      default: true,
      required: false,
    },
    // 点击Logo跳转地址
    routerLinkTo: {
      type: Object,
      default: () => ({ name: 'dashboard' }),
    },
  },
}
</script>
<style lang="less" scoped>
/*缩小首页布 局顶部的高度*/
@height: 70px;

.sider {
  box-shadow: none !important;
  .logo {
    height: @height !important;
    line-height: @height !important;
    box-shadow: none !important;
    transition: background 300ms;
    width: 100%;
    padding: 0 12px;
    display: flex;
    align-items: center;
    justify-content: center;

    .logo-link {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      flex-wrap: nowrap;
    }

    .logo-img {
      height: 32px;
      width: auto;
      vertical-align: middle;
    }

    .logo-text {
      color: #0364ff;
      font-size: 18px;
      line-height: 1;
      margin: 0;
      white-space: nowrap;
    }

    @media (max-width: 768px) {
      .logo-img {
        height: 28px;
      }
      .logo-text {
        font-size: 16px;
      }
    }

    @media (max-width: 480px) {
      .logo-img {
        height: 24px;
      }
      .logo-text {
        font-size: 14px;
      }
    }

    a {
      // color: white;
      // &:hover {
      //   color: rgba(255, 255, 255, 0.8);
      // }
    }
  }

  // &.light .logo {
  //   background-color: @primary-color;
  // }
}
</style>
